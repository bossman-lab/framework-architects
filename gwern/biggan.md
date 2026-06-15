# Making Anime With BigGAN

[Source](https://gwern.net/biggan)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Making Anime With BigGAN





Danbooru AI, BigGAN, Python, tutorial

Experiments in using BigGAN to generate anime faces and whole anime images; semi-successful.
            2019-02-04–2021-01-29
            in progress
            certainty: highly likely
            importance: 5
            backlinks
            similar
            bibliography

- BigGAN Advantages
- BigGAN Disadvantages

- BigGAN Transfer Learning

- Experiments

- BigGAN-PyTorch

- BigGAN: Danbooru2018-1K Experiments

- Danbooru2018-1K Dataset
- BigGAN-PyTorch Training

- BigGAN: ImageNet → Danbooru2018-1K
- BigGAN: 256px Danbooru2018-1K

- 256px Danbooru2018-1K Samples
- 256px BigGAN Downloads
- Evaluation


- Compare_gan

- Danbooru2019+e621 256px BigGAN




Following my StyleGAN anime face experiments, I explore BigGAN, another recent GAN with SOTA results on one of the most complex image domains tackled by GANs so far (ImageNet). BigGAN’s capabilities come at a steep compute cost, however.


Using the unofficial BigGAN-PyTorch reimplementation, I experimented in 2019 with 128px ImageNet transfer learning (successful) with ~6 GPU-days, and from-scratch 256px anime portraits of 1,000 characters on an 8


While BigGAN is not yet superior to StyleGAN for many purposes, BigGAN-like approaches may be necessary to scale to whole anime images.


For followup experiments, Shawn Presser, I and others (collectively, “Tensorfork”) have used Tensorflow Research Cloud TPU credits & the compare_gan BigGAN reimplementation. Running this at scale on the full Danbooru2019 dataset in May 2020, we have reached the best anime GAN results to date (later exceeded by This Anime Does Not Exist).


Just StyleGAN approaches have proven difficult and possibly inadequate to the ultimate goal, and motivated my evaluation of NNs which have demonstrated the ability to model much harder datasets like ImageNet at large pixel-sizes. The primary rival GAN to StyleGAN for large-scale image synthesis as of mid-2019 is BigGAN (Brock et al 2018; official BigGAN-PyTorch implementation & models).


BigGAN successfully trains on up to 512px images from ImageNet, from all 1,000 categories (conditioned on category), with near-photorealistic results on the best-represented categories (dogs), and apparently can even handle the far larger internal Google JFT dataset. In contrast, StyleGAN, while far less computationally demanding, shows poorer results on more complex categories (Karras et al 2018’s LSUN CATS StyleGAN; our whole-Danbooru2018 pilots) and has not been demonstrated to scale to ImageNet, much less beyond.

# BigGAN Advantages


BigGAN does this by combining a few improvements on standard DCGANs (most of which are not used in StyleGAN):

- 

architectural:

- 

residual layers
- 

self-attention layers (as in SAGAN)
- 

many more layers (which are wider/more channels, and deeper)
- 

class conditioning (1,000-category metadata)

- 

training:

- 

large minibatches (up to n = 2,048; either via using TPU clusters or by gradient accumulation over smaller minibatches)
- 

orthogonal regularization
- 

thorough hyperparameter sweeps to find good settings

- 

sample time:

- 

exponential moving average (EMA) on the Generator model (see also Gidel et al 2018, and compare with stochastic weight averaging (SWA))
- 

the truncation trick


Brock et al 2018: BigGAN-deep architecture (Figure 16, Table 5)


# BigGAN Disadvantages


The downside is that, as the name indicates, BigGAN is both a big model and requires big compute (particularly, big minibatches)—somewhere around $25,515.37$20,0002019, we estimate, based on public TPU pricing.


This present a dilemma: larger-scale portrait modeling or whole-anime image modeling may be beyond StyleGAN’s current capabilities; but while BigGAN may be able to handle those tasks, we can’t afford to train it!


Must it cost that much? Probably not. In particular, BigGAN’s use of a fixed large minibatch throughout training is probably inefficient: it is highly unlikely that the benefits of a n = 2,048 minibatch are necessary at the beginning of training when the Generator is generating static which looks nothing at all like real data, and at the end of training, that may still be too small a minibatch (Brock et al 2018 note that the benefits of larger minibatches had not saturated at n = 2,048 but time/compute was not available to test larger still minibatches, which is consistent with the gradient noise scale observation that the harder & more RL-like a problem, the larger the minibatch it needs). Typically, minibatches and/or learning rates are scheduled: imprecise gradients are acceptable early on, while as the model approaches perfection, more exact gradients are necessary. So it should be possible to start out with minibatches a tiny fraction of the size and gradually scale them up during training, saving an enormous amount of compute compared to BigGAN’s reported numbers. The gradient noise scale could be used to automatically set the total minibatch scale, although I didn’t find any examples of anyone using it in PyTorch this way. And using TPU pods provides large amounts of VRAM, but is not necessarily the cheapest form of compute.

## BigGAN Transfer Learning


Another optimization is to exploit transfer learning from the released models, and reuse the enormous amount of compute invested in them. The practical details there are fiddly. The original BigGAN 2018 release included the 128px/256px/512px Generator Tensorflow models but not their Discriminators, nor a training codebase; the `compare_gan` Tensorflow codebase released in early 2019 includes an independent implementation of BigGAN that can potentially train them, and I believe that the Generator may still be usable for transfer learning on its own and if not—given the arguments that Discriminators simply memorize data and do not learn much beyond that—the Discriminators can be trained from scratch by simply freezing a G while training its D on G outputs for as long as necessary. The 2019 PyTorch release includes a different model, a full 128px model with G/D (at 2 points in its training), and code to convert the original Tensorflow models into PyTorch format; the catch there is that the pretrained model must be loaded into exactly the same architecture, and while the PyTorch codebase defines the architecture for 32/64/128/256px BigGANs, it does not (as of 2019-06-04) define the architecture for a 512px BigGAN or BigGAN-deep (I tried but couldn’t get it quite right). It would also be possible to do model surgery and promote the 128px model to a 512px model, since the two upscaling blocks (128px → 256px and 256px → 512px) should be easy to learn (similar to my use of waifu2x to fake a 1024px StyleGAN anime face model). Anyway, the upshot is that one can only use the 128px/256px pretrained models; the 512px will be possible with a small update to the PyTorch codebase.


All in all, it is possible that BigGAN with some tweaks could be affordable to train. (At least, with some crowdfunding…)


# Experiments


## BigGAN-PyTorch


### BigGAN: Danbooru2018-1K Experiments


To test out the water, I ran three BigGAN experiments:

- 

I first experimented with retraining the ImageNet 128px model1.


That resulted in almost total mode collapse when I re-enabled G after 2 days; investigating, I realized that I had misunderstood: it was a brand-new BigGAN model, trained independently, and came with its fully-trained D already. Oops.
- 

transfer learning the 128px ImageNet PyTorch BigGAN model to the 1k anime portraits; successful with ~6 GPU-days
- 

training from scratch a 256px BigGAN-deep on the 1k portraits;


Partially successful after ~240 GPU-days: it reached comparable quality to StyleGAN before suffering serious mode collapse due, possibly, being forced to run with small minibatch sizes by BigGAN bugs


#### Danbooru2018-1K Dataset


Constructing D1k


Constructing a new Danbooru-1k dataset: as BigGAN requires conditioning information, I constructed new 512px whole-image & portrait datasets by taking the 1,000 most popular Danbooru2018 characters, with characters as categories, and cropped out portraits as usual:


`cat metadata/20180000000000* | grep -F -e '"name":"solo"' | grep -F -v '"rating":"e"' | \
    jq -c '.tags | .[] | select(.category == "4") | .name' | sort | uniq --count | \
    sort --numeric-sort > characters.txt
mkdir ./characters-1k/; cd ./characters-1k/
cpCharacterFace () { # }
    CHARACTER="$@"
    CHARACTER_SAFE=$(echo $CHARACTER | tr '[:punct:]' '.')
    mkdir "$CHARACTER_SAFE"
    echo "$CHARACTER" "$CHARACTER_SAFE"
    IDS=$(cat ../metadata/* | grep -F '"name":"'$CHARACTER\" | grep -F -e '"name":"solo"' \
          | grep -F -v '"rating":"e"' | jq .id | tr -d '"')
    for ID in $IDS; do
        BUCKET=$(printf "%04d" $(( $ID % 1000 )) );
        TARGET=$(ls ../original/$BUCKET/$ID.*)
        CUDA_VISIBLE_DEVICES="" nice python ~/src/lbpcascade_animeface/examples/crop.py \
            ~/src/lbpcascade_animeface/lbpcascade_animeface.xml "$TARGET" "./$CHARACTER_SAFE/$ID"
    done
    }
export -f cpCharacterFace
tail -1200 ../characters.txt | cut -d '"' -f 2 | parallel --progress cpCharacterFace`


I merged a number of redundant folders by hand2, cleaned as usual, and did further cropping as necessary to reach 1,000. This resulted in 212,359 portrait faces, with the largest class (Hatsune Miku) having 6,624 images and the smallest classes having ~0 or 1 images. (I don’t know if the class imbalance constitutes a real problem for BigGAN, as ImageNet itself is imbalanced on many levels.)


The data-loading code attempts to make the class index/ID number line up with the folder count, so the nth alphabetical folder (character) should have class ID n, which is important to know for generating conditional samples. The final set/IDs (as defined for my Danbooru 1K dataset by `find_classes`):


`2k.tan: 0 • abe.nana: 1 • abigail.williams..fate.grand.order.: 2 • abukuma..kantai.collection.: 3
admiral..kantai.collection.: 4 • aegis..persona.: 5 • aerith.gainsborough: 6 • afuro.terumi: 7
agano..kantai.collection.: 8 • agrias.oaks: 9 • ahri: 10 • aida.mana: 11
aino.minako: 12 • aisaka.taiga: 13 • aisha..elsword.: 14 • akagi..kantai.collection.: 15
akagi.miria: 16 • akashi..kantai.collection.: 17 • akatsuki..kantai.collection.: 18 • akaza.akari: 19
akebono..kantai.collection.: 20 • akemi.homura: 21 • aki.minoriko: 22 • aki.shizuha: 23
akigumo..kantai.collection.: 24 • akitsu.maru..kantai.collection.: 25 • akitsushima..kantai.collection.: 26 • akiyama.mio: 27
akiyama.yukari: 28 • akizuki..kantai.collection.: 29 • akizuki.ritsuko: 30 • akizuki.ryou: 31
akuma.homura: 32 • albedo: 33 • alice..wonderland.: 34 • alice.margatroid: 35
alice.margatroid..pc.98.: 36 • alisa.ilinichina.amiella: 37 • altera..fate.: 38 • amagi..kantai.collection.: 39
amagi.yukiko: 40 • amami.haruka: 41 • amanogawa.kirara: 42 • amasawa.yuuko: 43
amatsukaze..kantai.collection.: 44 • amazon..dragon.s.crown.: 45 • anastasia..idolmaster.: 46 • anchovy: 47
android.18: 48 • android.21: 49 • anegasaki.nene: 50 • angel..kof.: 51
angela.balzac: 52 • anjou.naruko: 53 • aoba..kantai.collection.: 54 • aoki.reika: 55
aori..splatoon.: 56 • aozaki.aoko: 57 • aqua..konosuba.: 58 • ara.han: 59
aragaki.ayase: 60 • araragi.karen: 61 • arashi..kantai.collection.: 62 • arashio..kantai.collection.: 63
archer: 64 • arcueid.brunestud: 65 • arima.senne: 66 • artoria.pendragon..all.: 67
artoria.pendragon..lancer.: 68 • artoria.pendragon..lancer.alter.: 69 • artoria.pendragon..swimsuit.rider.alter.: 70 • asahina.mikuru: 71
asakura.ryouko: 72 • asashimo..kantai.collection.: 73 • asashio..kantai.collection.: 74 • ashigara..kantai.collection.: 75
asia.argento: 76 • astolfo..fate.: 77 • asui.tsuyu: 78 • asuna..sao.: 79
atago..azur.lane.: 80 • atago..kantai.collection.: 81 • atalanta..fate.: 82 • au.ra: 83
ayanami..azur.lane.: 84 • ayanami..kantai.collection.: 85 • ayanami.rei: 86 • ayane..doa.: 87
ayase.eli: 88 • baiken: 89 • bardiche: 90 • barnaby.brooks.jr: 91
battleship.hime: 92 • bayonetta..character.: 93 • bb..fate...all.: 94 • bb..fate.extra.ccc.: 95
bb..swimsuit.mooncancer...fate.: 96 • beatrice: 97 • belfast..azur.lane.: 98 • bismarck..kantai.collection.: 99
black.hanekawa: 100 • black.rock.shooter..character.: 101 • blake.belladonna: 102 • blanc: 103
boko..girls.und.panzer.: 104 • bottle.miku: 105 • boudica..fate.grand.order.: 106 • bowsette: 107
bridget..guilty.gear.: 108 • busujima.saeko: 109 • c.c.: 110 • c.c..lemon..character.: 111
caesar.anthonio.zeppeli: 112 • cagliostro..granblue.fantasy.: 113 • camilla..fire.emblem.if.: 114 • cammy.white: 115
caren.hortensia: 116 • caster: 117 • cecilia.alcott: 118 • celes.chere: 119
charlotte..madoka.magica.: 120 • charlotte.dunois: 121 • charlotte.e.yeager: 122 • chen: 123
chibi.usa: 124 • chiki: 125 • chitanda.eru: 126 • chloe.von.einzbern: 127
choukai..kantai.collection.: 128 • chun.li: 129 • ciel: 130 • cirno: 131
clarisse..granblue.fantasy.: 132 • clownpiece: 133 • consort.yu..fate.: 134 • cure.beauty: 135
cure.happy: 136 • cure.march: 137 • cure.marine: 138 • cure.moonlight: 139
cure.peace: 140 • cure.sunny: 141 • cure.sunshine: 142 • cure.twinkle: 143
d.va..overwatch.: 144 • daiyousei: 145 • danua: 146 • darjeeling: 147
dark.magician.girl: 148 • dio.brando: 149 • dizzy: 150 • djeeta..granblue.fantasy.: 151
doremy.sweet: 152 • eas: 153 • eila.ilmatar.juutilainen: 154 • elesis..elsword.: 155
elin..tera.: 156 • elizabeth.bathory..brave...fate.: 157 • elizabeth.bathory..fate.: 158 • elizabeth.bathory..fate...all.: 159
ellen.baker: 160 • elphelt.valentine: 161 • elsa..frozen.: 162 • emilia..re.zero.: 163
emiya.kiritsugu: 164 • emiya.shirou: 165 • emperor.penguin..kemono.friends.: 166 • enma.ai: 167
enoshima.junko: 168 • enterprise..azur.lane.: 169 • ereshkigal..fate.grand.order.: 170 • erica.hartmann: 171
etna: 172 • eureka: 173 • eve..elsword.: 174 • ex.keine: 175
failure.penguin: 176 • fate.testarossa: 177 • felicia: 178 • female.admiral..kantai.collection.: 179
female.my.unit..fire.emblem.if.: 180 • female.protagonist..pokemon.go.: 181 • fennec..kemono.friends.: 182 • ferry..granblue.fantasy.: 183
flandre.scarlet: 184 • florence.nightingale..fate.grand.order.: 185 • fou..fate.grand.order.: 186 • francesca.lucchini: 187
frankenstein.s.monster..fate.: 188 • fubuki..kantai.collection.: 189 • fujibayashi.kyou: 190 • fujimaru.ritsuka..female.: 191
fujiwara.no.mokou: 192 • furude.rika: 193 • furudo.erika: 194 • furukawa.nagisa: 195
fusou..kantai.collection.: 196 • futaba.anzu: 197 • futami.mami: 198 • futatsuiwa.mamizou: 199
fuuro..pokemon.: 200 • galko: 201 • gambier.bay..kantai.collection.: 202 • ganaha.hibiki: 203
gangut..kantai.collection.: 204 • gardevoir: 205 • gasai.yuno: 206 • gertrud.barkhorn: 207
gilgamesh: 208 • ginga.nakajima: 209 • giorno.giovanna: 210 • gokou.ruri: 211
graf.eisen: 212 • graf.zeppelin..kantai.collection.: 213 • grey.wolf..kemono.friends.: 214 • gumi: 215
hachikuji.mayoi: 216 • hagikaze..kantai.collection.: 217 • hagiwara.yukiho: 218 • haguro..kantai.collection.: 219
hakurei.reimu: 220 • hamakaze..kantai.collection.: 221 • hammann..azur.lane.: 222 • han.juri: 223
hanasaki.tsubomi: 224 • hanekawa.tsubasa: 225 • hanyuu: 226 • haramura.nodoka: 227
harime.nui: 228 • haro: 229 • haruka..pokemon.: 230 • haruna..kantai.collection.: 231
haruno.sakura: 232 • harusame..kantai.collection.: 233 • hasegawa.kobato: 234 • hassan.of.serenity..fate.: 235
hata.no.kokoro: 236 • hatoba.tsugu..character.: 237 • hatsune.miku: 238 • hatsune.miku..append.: 239
hatsuyuki..kantai.collection.: 240 • hatsuzuki..kantai.collection.: 241 • hayami.kanade: 242 • hayashimo..kantai.collection.: 243
hayasui..kantai.collection.: 244 • hecatia.lapislazuli: 245 • helena.blavatsky..fate.grand.order.: 246 • heles: 247
hestia..danmachi.: 248 • hex.maniac..pokemon.: 249 • hibari..senran.kagura.: 250 • hibiki..kantai.collection.: 251
hieda.no.akyuu: 252 • hiei..kantai.collection.: 253 • higashi.setsuna: 254 • higashikata.jousuke: 255
high.priest: 256 • hiiragi.kagami: 257 • hiiragi.tsukasa: 258 • hijiri.byakuren: 259
hikari..pokemon.: 260 • himejima.akeno: 261 • himekaidou.hatate: 262 • hinanawi.tenshi: 263
hinatsuru.ai: 264 • hino.akane..idolmaster.: 265 • hino.akane..smile.precure..: 266 • hino.rei: 267
hirasawa.ui: 268 • hirasawa.yui: 269 • hiryuu..kantai.collection.: 270 • hishikawa.rikka: 271
hk416..girls.frontline.: 272 • holo: 273 • homura..xenoblade.2.: 274 • honda.mio: 275
hong.meiling: 276 • honma.meiko: 277 • honolulu..azur.lane.: 278 • horikawa.raiko: 279
hoshi.shouko: 280 • hoshiguma.yuugi: 281 • hoshii.miki: 282 • hoshimiya.ichigo: 283
hoshimiya.kate: 284 • hoshino.fumina: 285 • hoshino.ruri: 286 • hoshizora.miyuki: 287
hoshizora.rin: 288 • hotarumaru: 289 • hoto.cocoa: 290 • houjou.hibiki: 291
houjou.karen: 292 • houjou.satoko: 293 • houjuu.nue: 294 • houraisan.kaguya: 295
houshou..kantai.collection.: 296 • huang.baoling: 297 • hyuuga.hinata: 298 • i.168..kantai.collection.: 299
i.19..kantai.collection.: 300 • i.26..kantai.collection.: 301 • i.401..kantai.collection.: 302 • i.58..kantai.collection.: 303
i.8..kantai.collection.: 304 • ia..vocaloid.: 305 • ibaraki.douji..fate.grand.order.: 306 • ibaraki.kasen: 307
ibuki.fuuko: 308 • ibuki.suika: 309 • ichigo..darling.in.the.franxx.: 310 • ichinose.kotomi: 311
ichinose.shiki: 312 • ikamusume: 313 • ikazuchi..kantai.collection.: 314 • illustrious..azur.lane.: 315
illyasviel.von.einzbern: 316 • imaizumi.kagerou: 317 • inaba.tewi: 318 • inami.mahiru: 319
inazuma..kantai.collection.: 320 • index: 321 • ingrid: 322 • inkling: 323
inubashiri.momiji: 324 • inuyama.aoi: 325 • iori.rinko: 326 • iowa..kantai.collection.: 327
irisviel.von.einzbern: 328 • iroha..samurai.spirits.: 329 • ishtar..fate.grand.order.: 330 • isokaze..kantai.collection.: 331
isonami..kantai.collection.: 332 • isuzu..kantai.collection.: 333 • itsumi.erika: 334 • ivan.karelin: 335
izayoi.sakuya: 336 • izumi.konata: 337 • izumi.sagiri: 338 • jack.the.ripper..fate.apocrypha.: 339
jakuzure.nonon: 340 • japanese.crested.ibis..kemono.friends.: 341 • jeanne.d.arc..alter...fate.: 342 • jeanne.d.arc..alter.swimsuit.berserker.: 343
jeanne.d.arc..fate.: 344 • jeanne.d.arc..fate...all.: 345 • jeanne.d.arc..granblue.fantasy.: 346 • jeanne.d.arc..swimsuit.archer.: 347
jeanne.d.arc.alter.santa.lily: 348 • jintsuu..kantai.collection.: 349 • jinx..league.of.legends.: 350 • johnny.joestar: 351
jonathan.joestar: 352 • joseph.joestar..young.: 353 • jougasaki.mika: 354 • jougasaki.rika: 355
jun.you..kantai.collection.: 356 • junketsu: 357 • junko..touhou.: 358 • kaban..kemono.friends.: 359
kaburagi.t.kotetsu: 360 • kaenbyou.rin: 361 • kaenbyou.rin..cat.: 362 • kafuu.chino: 363
kaga..kantai.collection.: 364 • kagamine.len: 365 • kagamine.rin: 366 • kagerou..kantai.collection.: 367
kagiyama.hina: 368 • kagura..gintama.: 369 • kaguya.luna..character.: 370 • kaito: 371
kaku.seiga: 372 • kakyouin.noriaki: 373 • kallen.stadtfeld: 374 • kamikaze..kantai.collection.: 375
kamikita.komari: 376 • kamio.misuzu: 377 • kamishirasawa.keine: 378 • kamiya.nao: 379
kamoi..kantai.collection.: 380 • kaname.madoka: 381 • kanbaru.suruga: 382 • kanna.kamui: 383
kanzaki.ranko: 384 • karina.lyle: 385 • kasane.teto: 386 • kashima..kantai.collection.: 387
kashiwazaki.sena: 388 • kasodani.kyouko: 389 • kasugano.sakura: 390 • kasugano.sora: 391
kasumi..doa.: 392 • kasumi..kantai.collection.: 393 • kasumi..pokemon.: 394 • kasumigaoka.utaha: 395
katori..kantai.collection.: 396 • katou.megumi: 397 • katsura.hinagiku: 398 • katsuragi..kantai.collection.: 399
katsushika.hokusai..fate.grand.order.: 400 • katyusha: 401 • kawakami.mai: 402 • kawakaze..kantai.collection.: 403
kawashiro.nitori: 404 • kay..girls.und.panzer.: 405 • kazama.asuka: 406 • kazami.yuuka: 407
kenzaki.makoto: 408 • kijin.seija: 409 • kikuchi.makoto: 410 • kino: 411
kino.makoto: 412 • kinomoto.sakura: 413 • kinugasa..kantai.collection.: 414 • kirigaya.suguha: 415
kirigiri.kyouko: 416 • kirijou.mitsuru: 417 • kirima.sharo: 418 • kirin..armor.: 419
kirino.ranmaru: 420 • kirisame.marisa: 421 • kirishima..kantai.collection.: 422 • kirito: 423
kiryuuin.satsuki: 424 • kisaragi..kantai.collection.: 425 • kisaragi.chihaya: 426 • kise.yayoi: 427
kishibe.rohan: 428 • kishin.sagume: 429 • kiso..kantai.collection.: 430 • kiss.shot.acerola.orion.heart.under.blade: 431
kisume: 432 • kitakami..kantai.collection.: 433 • kiyohime..fate.grand.order.: 434 • kiyoshimo..kantai.collection.: 435
kizuna.ai: 436 • koakuma: 437 • kobayakawa.rinko: 438 • kobayakawa.sae: 439
kochiya.sanae: 440 • kohinata.miho: 441 • koizumi.hanayo: 442 • komaki.manaka: 443
komeiji.koishi: 444 • komeiji.satori: 445 • kongou..kantai.collection.: 446 • konjiki.no.yami: 447
konpaku.youmu: 448 • konpaku.youmu..ghost.: 449 • kooh: 450 • kos.mos: 451
koshimizu.sachiko: 452 • kotobuki.tsumugi: 453 • kotomine.kirei: 454 • kotonomiya.yuki: 455
kousaka.honoka: 456 • kousaka.kirino: 457 • kousaka.tamaki: 458 • kozakura.marry: 459
kuchiki.rukia: 460 • kujikawa.rise: 461 • kujou.karen: 462 • kula.diamond: 463
kuma..kantai.collection.: 464 • kumano..kantai.collection.: 465 • kumoi.ichirin: 466 • kunikida.hanamaru: 467
kuradoberi.jam: 468 • kuriyama.mirai: 469 • kurodani.yamame: 470 • kuroka..high.school.dxd.: 471
kurokawa.eren: 472 • kuroki.tomoko: 473 • kurosawa.dia: 474 • kurosawa.ruby: 475
kuroshio..kantai.collection.: 476 • kuroyukihime: 477 • kurumi.erika: 478 • kusanagi.motoko: 479
kusugawa.sasara: 480 • kuujou.jolyne: 481 • kuujou.joutarou: 482 • kyon: 483
kyonko: 484 • kyubey: 485 • laffey..azur.lane.: 486 • lala.satalin.deviluke: 487
lancer: 488 • lancer..fate.zero.: 489 • laura.bodewig: 490 • leafa: 491
lei.lei: 492 • lelouch.lamperouge: 493 • len: 494 • letty.whiterock: 495
levi..shingeki.no.kyojin.: 496 • libeccio..kantai.collection.: 497 • lightning.farron: 498 • lili..tekken.: 499
lilith.aensland: 500 • lillie..pokemon.: 501 • lily.white: 502 • link: 503
little.red.riding.hood..grimm.: 504 • louise.francoise.le.blanc.de.la.valliere: 505 • lucina: 506 • lum: 507
luna.child: 508 • lunamaria.hawke: 509 • lunasa.prismriver: 510 • lusamine..pokemon.: 511
lyn..blade...soul.: 512 • lyndis..fire.emblem.: 513 • lynette.bishop: 514 • m1903.springfield..girls.frontline.: 515
madotsuki: 516 • maekawa.miku: 517 • maka.albarn: 518 • makigumo..kantai.collection.: 519
makinami.mari.illustrious: 520 • makise.kurisu: 521 • makoto..street.fighter.: 522 • makoto.nanaya: 523
mankanshoku.mako: 524 • mao..pokemon.: 525 • maou..maoyuu.: 526 • maribel.hearn: 527
marie.antoinette..fate.grand.order.: 528 • mash.kyrielight: 529 • matoi..pso2.: 530 • matoi.ryuuko: 531
matou.sakura: 532 • matsuura.kanan: 533 • maya..kantai.collection.: 534 • me.tan: 535
medicine.melancholy: 536 • medjed: 537 • meer.campbell: 538 • megumin: 539
megurine.luka: 540 • mei..overwatch.: 541 • mei..pokemon.: 542 • meiko: 543
meltlilith: 544 • mercy..overwatch.: 545 • merlin.prismriver: 546 • michishio..kantai.collection.: 547
midare.toushirou: 548 • midna: 549 • midorikawa.nao: 550 • mika..girls.und.panzer.: 551
mikasa.ackerman: 552 • mikazuki.munechika: 553 • miki.sayaka: 554 • millia.rage: 555
mima: 556 • mimura.kanako: 557 • minami.kotori: 558 • minamoto.no.raikou..fate.grand.order.: 559
minamoto.no.raikou..swimsuit.lancer...fate.: 560 • minase.akiko: 561 • minase.iori: 562 • miqo.te: 563
misaka.mikoto: 564 • mishaguji: 565 • misumi.nagisa: 566 • mithra: 567
miura.azusa: 568 • miyafuji.yoshika: 569 • miyako.yoshika: 570 • miyamoto.frederica: 571
miyamoto.musashi..fate.grand.order.: 572 • miyaura.sanshio: 573 • mizuhashi.parsee: 574 • mizuki..pokemon.: 575
mizunashi.akari: 576 • mizuno.ami: 577 • mogami..kantai.collection.: 578 • momo.velia.deviluke: 579
momozono.love: 580 • mononobe.no.futo: 581 • mordred..fate.: 582 • mordred..fate...all.: 583
morgiana: 584 • morichika.rinnosuke: 585 • morikubo.nono: 586 • moriya.suwako: 587
moroboshi.kirari: 588 • morrigan.aensland: 589 • motoori.kosuzu: 590 • mumei..kabaneri.: 591
murakumo..kantai.collection.: 592 • murasa.minamitsu: 593 • murasame..kantai.collection.: 594 • musashi..kantai.collection.: 595
mutsu..kantai.collection.: 596 • mutsuki..kantai.collection.: 597 • my.unit..fire.emblem..kakusei.: 598 • my.unit..fire.emblem.if.: 599
myoudouin.itsuki: 600 • mysterious.heroine.x: 601 • mysterious.heroine.x..alter.: 602 • mystia.lorelei: 603
nadia: 604 • nagae.iku: 605 • naganami..kantai.collection.: 606 • nagato..kantai.collection.: 607
nagato.yuki: 608 • nagatsuki..kantai.collection.: 609 • nagi: 610 • nagisa.kaworu: 611
naka..kantai.collection.: 612 • nakano.azusa: 613 • nami..one.piece.: 614 • nanami.chiaki: 615
nanasaki.ai: 616 • nao..mabinogi.: 617 • narmaya..granblue.fantasy.: 618 • narukami.yuu: 619
narusawa.ryouka: 620 • natalia..idolmaster.: 621 • natori.sana: 622 • natsume..pokemon.: 623
natsume.rin: 624 • nazrin: 625 • nekomiya.hinata: 626 • nekomusume: 627
nekomusume..gegege.no.kitarou.6.: 628 • nepgear: 629 • neptune..neptune.series.: 630 • nero.claudius..bride...fate.: 631
nero.claudius..fate.: 632 • nero.claudius..fate...all.: 633 • nero.claudius..swimsuit.caster...fate.: 634 • nia.teppelin: 635
nibutani.shinka: 636 • nico.robin: 637 • ninomiya.asuka: 638 • nishikino.maki: 639
nishizumi.maho: 640 • nishizumi.miho: 641 • nitocris..fate.grand.order.: 642 • nitocris..swimsuit.assassin...fate.: 643
nitta.minami: 644 • noel.vermillion: 645 • noire: 646 • northern.ocean.hime: 647
noshiro..kantai.collection.: 648 • noumi.kudryavka: 649 • nu.13: 650 • nyarlathotep..nyaruko.san.: 651
oboro..kantai.collection.: 652 • oda.nobunaga..fate.: 653 • ogata.chieri: 654 • ohara.mari: 655
oikawa.shizuku: 656 • okazaki.yumemi: 657 • okita.souji..alter...fate.: 658 • okita.souji..fate.: 659
okita.souji..fate...all.: 660 • onozuka.komachi: 661 • ooi..kantai.collection.: 662 • oomori.yuuko: 663
ootsuki.yui: 664 • ooyodo..kantai.collection.: 665 • osakabe.hime..fate.grand.order.: 666 • oshino.shinobu: 667
otonashi.kotori: 668 • panty..psg.: 669 • passion.lip: 670 • patchouli.knowledge: 671
pepperoni..girls.und.panzer.: 672 • perrine.h.clostermann: 673 • pharah..overwatch.: 674 • phosphophyllite: 675
pikachu: 676 • pixiv.tan: 677 • platelet..hataraku.saibou.: 678 • platinum.the.trinity: 679
pod..nier.automata.: 680 • pola..kantai.collection.: 681 • priest..ragnarok.online.: 682 • princess.king.boo: 683
princess.peach: 684 • princess.serenity: 685 • princess.zelda: 686 • prinz.eugen..azur.lane.: 687
prinz.eugen..kantai.collection.: 688 • prisma.illya: 689 • purple.heart: 690 • puru.see: 691
pyonta: 692 • qbz.95..girls.frontline.: 693 • rachel.alucard: 694 • racing.miku: 695
raising.heart: 696 • ramlethal.valentine: 697 • ranka.lee: 698 • ranma.chan: 699
re.class.battleship: 700 • reinforce: 701 • reinforce.zwei: 702 • reisen.udongein.inaba: 703
reiuji.utsuho: 704 • reizei.mako: 705 • rem..re.zero.: 706 • remilia.scarlet: 707
rensouhou.chan: 708 • rensouhou.kun: 709 • rias.gremory: 710 • rider: 711
riesz: 712 • ringo..touhou.: 713 • ro.500..kantai.collection.: 714 • roll: 715
rosehip: 716 • rossweisse: 717 • ruby.rose: 718 • rumia: 719
rydia: 720 • ryougi.shiki: 721 • ryuuguu.rena: 722 • ryuujou..kantai.collection.: 723
saber: 724 • saber.alter: 725 • saber.lily: 726 • sagisawa.fumika: 727
saigyouji.yuyuko: 728 • sailor.mars: 729 • sailor.mercury: 730 • sailor.moon: 731
sailor.saturn: 732 • sailor.venus: 733 • saint.martha: 734 • sakagami.tomoyo: 735
sakamoto.mio: 736 • sakata.gintoki: 737 • sakuma.mayu: 738 • sakura.chiyo: 739
sakura.futaba: 740 • sakura.kyouko: 741 • sakura.miku: 742 • sakurai.momoka: 743
sakurauchi.riko: 744 • samidare..kantai.collection.: 745 • samus.aran: 746 • sanya.v.litvyak: 747
sanzen.in.nagi: 748 • saotome.ranma: 749 • saratoga..kantai.collection.: 750 • sasaki.chiho: 751
saten.ruiko: 752 • satonaka.chie: 753 • satsuki..kantai.collection.: 754 • sawamura.spencer.eriri: 755
saya: 756 • sazaki.kaoruko: 757 • sazanami..kantai.collection.: 758 • scathach..fate...all.: 759
scathach..fate.grand.order.: 760 • scathach..swimsuit.assassin...fate.: 761 • seaport.hime: 762 • seeu: 763
seiran..touhou.: 764 • seiren..suite.precure.: 765 • sekibanki: 766 • selvaria.bles: 767
sendai..kantai.collection.: 768 • sendai.hakurei.no.miko: 769 • sengoku.nadeko: 770 • senjougahara.hitagi: 771
senketsu: 772 • sento.isuzu: 773 • serena..pokemon.: 774 • serval..kemono.friends.: 775
sf.a2.miki: 776 • shameimaru.aya: 777 • shana: 778 • shanghai.doll: 779
shantae..character.: 780 • sheryl.nome: 781 • shibuya.rin: 782 • shidare.hotaru: 783
shigure..kantai.collection.: 784 • shijou.takane: 785 • shiki.eiki: 786 • shikinami..kantai.collection.: 787
shikinami.asuka.langley: 788 • shimada.arisu: 789 • shimakaze..kantai.collection.: 790 • shimamura.uzuki: 791
shinjou.akane: 792 • shinki: 793 • shinku: 794 • shiomi.shuuko: 795
shirabe.ako: 796 • shirai.kuroko: 797 • shirakiin.ririchiyo: 798 • shiranui..kantai.collection.: 799
shiranui.mai: 800 • shirasaka.koume: 801 • shirase.sakuya: 802 • shiratsuyu..kantai.collection.: 803
shirayuki.hime: 804 • shirogane.naoto: 805 • shirona..pokemon.: 806 • shoebill..kemono.friends.: 807
shokuhou.misaki: 808 • shouhou..kantai.collection.: 809 • shoukaku..kantai.collection.: 810 • shuten.douji..fate.grand.order.: 811
signum: 812 • silica: 813 • simon: 814 • sinon: 815
soga.no.tojiko: 816 • sona.buvelle: 817 • sonoda.umi: 818 • sonohara.anri: 819
sonozaki.mion: 820 • sonozaki.shion: 821 • sora.ginko: 822 • sorceress..dragon.s.crown.: 823
souryuu..kantai.collection.: 824 • souryuu.asuka.langley: 825 • souseiseki: 826 • star.sapphire: 827
stocking..psg.: 828 • su.san: 829 • subaru.nakajima: 830 • suigintou: 831
suiren..pokemon.: 832 • suiseiseki: 833 • sukuna.shinmyoumaru: 834 • sunny.milk: 835
suomi.kp31..girls.frontline.: 836 • super.pochaco: 837 • super.sonico: 838 • suzukaze.aoba: 839
suzumiya.haruhi: 840 • suzutsuki..kantai.collection.: 841 • suzuya..kantai.collection.: 842 • tachibana.arisu: 843
tachibana.hibiki..symphogear.: 844 • tada.riina: 845 • taigei..kantai.collection.: 846 • taihou..azur.lane.: 847
taihou..kantai.collection.: 848 • tainaka.ritsu: 849 • takagaki.kaede: 850 • takakura.himari: 851
takamachi.nanoha: 852 • takami.chika: 853 • takanashi.rikka: 854 • takao..azur.lane.: 855
takao..kantai.collection.: 856 • takara.miyuki: 857 • takarada.rikka: 858 • takatsuki.yayoi: 859
takebe.saori: 860 • tama..kantai.collection.: 861 • tamamo..fate...all.: 862 • tamamo.cat..fate.: 863
tamamo.no.mae..fate.: 864 • tamamo.no.mae..swimsuit.lancer...fate.: 865 • tanamachi.kaoru: 866 • taneshima.popura: 867
tanned.cirno: 868 • taokaka: 869 • tatara.kogasa: 870 • tateyama.ayano: 871
tatsumaki: 872 • tatsuta..kantai.collection.: 873 • tedeza.rize: 874 • tenryuu..kantai.collection.: 875
tenshi..angel.beats..: 876 • teruzuki..kantai.collection.: 877 • tharja: 878 • tifa.lockhart: 879
tina.branford: 880 • tippy..gochiusa.: 881 • tokiko..touhou.: 882 • tokisaki.kurumi: 883
tokitsukaze..kantai.collection.: 884 • tomoe.gozen..fate.grand.order.: 885 • tomoe.hotaru: 886 • tomoe.mami: 887
tone..kantai.collection.: 888 • toono.akiha: 889 • tooru..maidragon.: 890 • toosaka.rin: 891
toramaru.shou: 892 • toshinou.kyouko: 893 • totoki.airi: 894 • toudou.shimako: 895
toudou.yurika: 896 • toujou.koneko: 897 • toujou.nozomi: 898 • touko..pokemon.: 899
touwa.erio: 900 • toyosatomimi.no.miko: 901 • tracer..overwatch.: 902 • tsukikage.yuri: 903
tsukimiya.ayu: 904 • tsukino.mito: 905 • tsukino.usagi: 906 • tsukumo.benben: 907
tsurumaru.kuninaga: 908 • tsuruya: 909 • tsushima.yoshiko: 910 • u.511..kantai.collection.: 911
ujimatsu.chiya: 912 • ultimate.madoka: 913 • umikaze..kantai.collection.: 914 • unicorn..azur.lane.: 915
unryuu..kantai.collection.: 916 • urakaze..kantai.collection.: 917 • uraraka.ochako: 918 • usada.hikaru: 919
usami.renko: 920 • usami.sumireko: 921 • ushio..kantai.collection.: 922 • ushiromiya.ange: 923
ushiwakamaru..fate.grand.order.: 924 • uzuki..kantai.collection.: 925 • vampire..azur.lane.: 926 • vampy: 927
venera.sama: 928 • verniy..kantai.collection.: 929 • victorica.de.blois: 930 • violet.evergarden..character.: 931
vira.lilie: 932 • vita: 933 • vivio: 934 • wa2000..girls.frontline.: 935
wakasagihime: 936 • wang.liu.mei: 937 • warspite..kantai.collection.: 938 • watanabe.you: 939
watarase.jun: 940 • watatsuki.no.yorihime: 941 • waver.velvet: 942 • weiss.schnee: 943
white.mage: 944 • widowmaker..overwatch.: 945 • wo.class.aircraft.carrier: 946 • wriggle.nightbug: 947
xenovia.quarta: 948 • xp.tan: 949 • xuanzang..fate.grand.order.: 950 • yagami.hayate: 951
yagokoro.eirin: 952 • yahagi..kantai.collection.: 953 • yakumo.ran: 954 • yakumo.yukari: 955
yamada.aoi: 956 • yamada.elf: 957 • yamakaze..kantai.collection.: 958 • yamashiro..azur.lane.: 959
yamashiro..kantai.collection.: 960 • yamato..kantai.collection.: 961 • yamato.no.kami.yasusada: 962 • yang.xiao.long: 963
yasaka.kanako: 964 • yayoi..kantai.collection.: 965 • yazawa.nico: 966 • yin: 967
yoko.littner: 968 • yorha.no..2.type.b: 969 • yorigami.shion: 970 • yowane.haku: 971
yuffie.kisaragi: 972 • yui..angel.beats..: 973 • yuigahama.yui: 974 • yuki.miku: 975
yukikaze..kantai.collection.: 976 • yukine.chris: 977 • yukinoshita.yukino: 978 • yukishiro.honoka: 979
yumi..senran.kagura.: 980 • yuna..ff10.: 981 • yuno: 982 • yura..kantai.collection.: 983
yuubari..kantai.collection.: 984 • yuudachi..kantai.collection.: 985 • yuugumo..kantai.collection.: 986 • yuuki..sao.: 987
yuuki.makoto: 988 • yuuki.mikan: 989 • yuzuhara.konomi: 990 • yuzuki.yukari: 991
yuzuriha.inori: 992 • z1.leberecht.maass..kantai.collection.: 993 • z3.max.schultz..kantai.collection.: 994 • zero.two..darling.in.the.franxx.: 995
zeta..granblue.fantasy.: 996 • zooey..granblue.fantasy.: 997 • zuihou..kantai.collection.: 998 • zuikaku..kantai.collection.: 999`


(Aside from being potentially useful to stabilize training by providing supervision/metadata, use of classes/categories reduces the need for character-specific transfer learning for specialized StyleGAN models, since you can just generate samples from a specific class. For the 256px model, I provide downloadable samples for each of the 1,000 classes.)


D1K Download


D1K (20GB; n = 822,842 512px JPEGs) and the portrait-crop version, D1K-portraits (18GB; n = 212,359) are available for download:


`rsync --verbose --recursive rsync://176.9.41.242:873/biggan/d1k/ ./d1k/`


The JPG compression turned out to be too aggressive and result in noticeable artifacting, so in early 2020 I regenerated D1k from Danbooru2019 for future projects, creating D1K-2019-512px: a fresh set of top-1k solo character images, s/q Danbooru2019, no JPEG compression.


Merges of overlapping characters were again necessary; the full set of tag merges:


`m() { mv ./$1/* ./$2/ && rmdir ./$1; }
m alice.margatroid..pc.98. alice.margatroid; m artoria.pendragon..all. saber; m artoria.pendragon..lancer. saber;
m artoria.pendragon..lancer.alter. saber; m artoria.pendragon..swimsuit.rider.alter. saber; m artoria.pendragon..swimsuit.ruler...fate. saber;
m atago..midsummer.march...azur.lane. atago..azur.lane.; m bardiche fate.testarossa; m bb..fate...all. matou.sakura;
m bb..fate.extra.ccc. matou.sakura; m bb..swimsuit.mooncancer...fate. matou.sakura; m bottle.miku hatsune.miku;
m cure.beauty aoki.reika; m cure.happy hoshizora.miyuki; m cure.march midorikawa.nao;
m cure.marine kurumi.erika; m cure.melody houjou.hibiki; m cure.moonlight tsukikage.yuri;
m cure.peace kise.yayoi; m cure.peach momozono.love; m cure.sunny hino.akane..smile.precure..;
m cure.sunshine myoudouin.itsuki; m cure.sword kenzaki.makoto; m cure.twinkle amanogawa.kirara;
m eas higashi.setsuna; m elizabeth.bathory..brave...fate. elizabeth.bathory..fate.; m elizabeth.bathory..fate...all. elizabeth.bathory..fate.;
m ex.keine kamishirasawa.keine; m frankenstein.s.monster..swimsuit.saber...fate. frankenstein.s.monster..fate.; m frederica.bernkastel furude.rika;
m furudo.erika furude.rika; m graf.eisen vita; m hatsune.miku..append. hatsune.miku;
m ishtar..fate.grand.order. ishtar..fate...all.; m jeanne.d.arc..alter...fate. jeanne.d.arc..fate.; m jeanne.d.arc..alter.swimsuit.berserker. jeanne.d.arc..fate.;
m jeanne.d.arc..fate...all. jeanne.d.arc..fate.; m jeanne.d.arc..swimsuit.archer. jeanne.d.arc..fate.; m jeanne.d.arc.alter.santa.lily jeanne.d.arc..fate.;
m kaenbyou.rin..cat. kaenbyou.rin; m kiyohime..swimsuit.lancer...fate. kiyohime..fate.grand.order.; m konpaku.youmu..ghost. konpaku.youmu;
m kyonko kyon; m lancer cu.chulainn..fate...all.; m medb..fate.grand.order. medb..fate...all.;
m medjed nitocris..fate.grand.order.; m meltryllis..swimsuit.lancer...fate. meltryllis; m minamoto.no.raikou..swimsuit.lancer...fate. minamoto.no.raikou..fate.grand.order.;
m miyamoto.musashi..swimsuit.berserker...fate. miyamoto.musashi..fate.grand.order.; m mordred..fate...all. mordred..fate.; m mysterious.heroine.x saber;
m mysterious.heroine.x..alter. saber; m mysterious.heroine.xx..foreigner. saber; m nero.claudius..bride...fate. nero.claudius..fate.;
m nero.claudius..fate...all. nero.claudius..fate.; m nero.claudius..swimsuit.caster...fate. nero.claudius..fate.; m nitocris..swimsuit.assassin...fate. nitocris..fate.grand.order.;
m oda.nobunaga..fate...all. oda.nobunaga..fate.; m okita.souji..alter...fate. okita.souji..fate.; m okita.souji..fate...all. okita.souji..fate.;
m princess.of.the.crystal takakura.himari; m princess.serenity tsukino.usagi; m prinz.eugen..unfading.smile...azur.lane. prinz.eugen..azur.lane.;
m prisma.illya illyasviel.von.einzbern; m purple.heart neptune..neptune.series.; m pyonta moriya.suwako;
m racing.miku hatsune.miku; m raising.heart takamachi.nanoha; m reinforce.zwei reinforce;
m rensouhou.chan shimakaze..kantai.collection.; m roll.caskett roll; m saber.alter saber;
m saber.lily saber; m sailor.jupiter kino.makoto; m sailor.mars hino.rei;
m sailor.mercury mizuno.ami; m sailor.moon tsukino.usagi; m sailor.saturn tomoe.hotaru;
m sailor.venus aino.minako; m sakura.miku hatsune.miku; m scathach..fate.grand.order. scathach..fate...all.;
m scathach..swimsuit.assassin...fate. scathach..fate...all.; m scathach.skadi..fate.grand.order. scathach..fate...all.; m schwertkreuz yagami.hayate;
m seiren..suite.precure. kurokawa.eren; m shanghai.doll alice.margatroid; m shikinami.asuka.langley souryuu.asuka.langley;
m su.san medicine.melancholy; m taihou..forbidden.feast...azur.lane. taihou..azur.lane.; m tamamo..fate...all. tamamo.cat..fate.;
m tamamo.no.mae..fate. tamamo.cat..fate.; m tamamo.no.mae..swimsuit.lancer...fate. tamamo.cat..fate.; m tanned.cirno cirno;
m ultimate.madoka kaname.madoka; m yuki.miku hatsune.miku`


Download:


`rsync --verbose --recursive rsync://176.9.41.242:873/biggan/d1k-2019-512px/ ./d1k-2019-512px/`


D1K BigGAN Conversion


BigGAN requires the dataset metadata to be defined in `utils.py`, and then, if using HDF5 archives it must be processed into a HDF5 archive, along with Inception statistics for the periodic testing (although I minimize testing, the preprocessed statistics are still necessary).


HDF5 is not necessary and can be omitted, BigGAN-Pytorch can read image folders, if you prefer to avoid the hassle.


The `utils.py` must be edited to add metadata per dataset (no CLI), which looks like this to define a 128px Danbooru-1k portrait dataset:


` # Convenience dicts
-dset_dict = {'I32': dset.ImageFolder, 'I64': dset.ImageFolder,
+dset_dict = {'I32': dset.ImageFolder, 'I64': dset.ImageFolder,
              'I128': dset.ImageFolder, 'I256': dset.ImageFolder,
              'I32_hdf5': dset.ILSVRC_HDF5, 'I64_hdf5': dset.ILSVRC_HDF5,
              'I128_hdf5': dset.ILSVRC_HDF5, 'I256_hdf5': dset.ILSVRC_HDF5,
-             'C10': dset.CIFAR​10, 'C100': dset.CIFAR​100}
+             'C10': dset.CIFAR​10, 'C100': dset.CIFAR​100,
+             'D1K': dset.ImageFolder, 'D1K_hdf5': dset.ILSVRC_HDF5 }
 imsize_dict = {'I32': 32, 'I32_hdf5': 32,
                'I64': 64, 'I64_hdf5': 64,
                'I128': 128, 'I128_hdf5': 128,
                'I256': 256, 'I256_hdf5': 256,
-               'C10': 32, 'C100': 32}
+               'C10': 32, 'C100': 32,
+               'D1K': 128, 'D1K_hdf5': 128 }
 root_dict = {'I32': 'ImageNet', 'I32_hdf5': 'ILSVRC32.hdf5',
              'I64': 'ImageNet', 'I64_hdf5': 'ILSVRC64.hdf5',
              'I128': 'ImageNet', 'I128_hdf5': 'ILSVRC128.hdf5',
              'I256': 'ImageNet', 'I256_hdf5': 'ILSVRC256.hdf5',
-             'C10': 'cifar', 'C100': 'cifar'}
+             'C10': 'cifar', 'C100': 'cifar',
+             'D1K': 'characters-1k-faces', 'D1K_hdf5': 'D1K.hdf5' }
 nclass_dict = {'I32': 1000, 'I32_hdf5': 1000,
                'I64': 1000, 'I64_hdf5': 1000,
                'I128': 1000, 'I128_hdf5': 1000,
                'I256': 1000, 'I256_hdf5': 1000,
-               'C10': 10, 'C100': 100}
-# Number of classes to put per sample sheet
+               'C10': 10, 'C100': 100,
+               'D1K': 1000, 'D1K_hdf5': 1000 }
+# Number of classes to put per sample sheet
 classes_per_sheet_dict = {'I32': 50, 'I32_hdf5': 50,
                           'I64': 50, 'I64_hdf5': 50,
                           'I128': 20, 'I128_hdf5': 20,
                           'I256': 20, 'I256_hdf5': 20,
-                          'C10': 10, 'C100': 100}
+                          'C10': 10, 'C100': 100,
+                          'D1K': 1, 'D1K_hdf5': 1 }`


Each dataset exists in 2 forms, as the original image folder and then as the processed HDF5:


`python make_hdf5.py --dataset D1K512 --data_root /media/gwern/Data2/danbooru2018
python calculate_inception_moments.py --parallel --dataset D1K_hdf5 --batch_size 64 \
    --data_root /media/gwern/Data2/danbooru2018
## Or ImageNet example:
python make_hdf5.py --dataset I128 --data_root /media/gwern/Data/imagenet/
python calculate_inception_moments.py --dataset I128_hdf5 --batch_size 64 \
    --data_root /media/gwern/Data/imagenet/`


`make_hdf5.py` will write the HDF5 to a `ILSVRC*.hdf5` file, so rename it to whatever (eg. `D1K.hdf5`).


#### BigGAN-PyTorch Training


With the HDF5 & Inception statistics calculated, it should be possible to run like so:


`python train.py --dataset D1K --parallel --shuffle --num_workers 4 --batch_size 32 \
    --num_G_accumulations 8 --num_D_accumulations 8 \
    --num_D_steps 1 --G_lr 1e-4 --D_lr 4e-4 --D_B2 0.999 --G_B2 0.999 --G_attn 64 --D_attn 64 \
    --G_nl inplace_relu --D_nl inplace_relu --SN_eps 1e-6 --BN_eps 1e-5 --adam_eps 1e-6 \
    --G_ortho 0.0 --G_shared --G_init ortho --D_init ortho --hier --dim_z 120 --shared_dim 128 \
    --G_eval_mode --G_ch 96 --D_ch 96 \
    --ema --use_ema --ema_start 20000 --test_every 2000 --save_every 1000 --num_best_copies 5 \
    --num_save_copies 2 --seed 0 --use_multiepoch_sampler --which_best FID \
    --data_root /media/gwern/Data2/danbooru2018`


The architecture is specified on the command line and must be correct; examples are in the `scripts/` directory. In the above example, `--num_D_steps...--D_ch` should be left strictly alone and the key parameters are before/after that architecture block. In this example, my 2×1080ti can support a batch size of n = 32 & the gradient accumulation overhead without OOMing. In addition to that, it’s important to enable EMA, which makes a truly remarkable difference in the generated sample quality (which is interesting because EMA sounds redundant with momentum/learning rates, but isn’t). The big batches of BigGAN are implemented by `--batch_size` times `--num_{G/D}_accumulations`; I would need an accumulation of 64 to match n = 2,048. Without EMA, samples are low quality and change drastically at each iteration; but after a certain number of iterations, sampling is done with EMA, which averages each iteration offline (but one doesn’t train using the averaged model!3), shows that collectively these iterations are similar because they are ‘orbiting’ around a central point and the image quality is clearly gradually improving when EMA is turned on.


Transfer learning is not supported natively, but a similar trick as with StyleGAN is feasible: just drop the pretrained models into the checkpoint folder and resume (which will work as long as the architecture is identical to the CLI parameters).


The sample sheet functionality can easily overload a GPU and OOM. In `utils.py`, it may be necessary to simply comment out all of the sampling functionality starting with `utils.sample_sheet`.


The main problem running BigGAN is odd bugs in BigGAN’s handling of epochs/iterations and changing gradient accumulations. With `--use_multiepoch_sampler`, it does complicated calculations to try to keep sampling consistent across epochs with precisely the same ordering of samples regardless of how often the BigGAN job is started/stopped (eg. on a cluster), but as one increases the total minibatch size and it progresses through an epoch, it tries to index data which doesn’t exist and crashes; I was unable to figure out how the calculations were going wrong, exactly.4


While with that option disabled and larger total minibatches used, a different bug gets triggered, leading to inscrutable crashes:


`# ...
# ERROR: Unexpected bus error encountered in worker. This might be caused by insufficient shared memory (shm).
# Traceback (most recent call last):
#   File "train.py", line 228, in <module>
#     main()
#   File "train.py", line 225, in main
#     run(config)
#   File "train.py", line 172, in run
#     for i, (x, y) in enumerate(pbar):
#   File "/root/BigGAN-PyTorch-mooch/utils.py", line 842, in progress
# 1    for n, item in enumerate(items):
#   File "/opt/conda/lib/python3.7/site-packages/torch/utils/data/dataloader.py", line 631, in __next__
#     idx, batch = self._get_batch()
#   File "/opt/conda/lib/python3.7/site-packages/torch/utils/data/dataloader.py", line 601, in _get_batch
#     return self.data_queue.get(timeout=MP_STATUS_CHECK_INTERVAL)
#   File "/opt/conda/lib/python3.7/queue.py", line 179, in get
#     self.not_empty.wait(remaining)
#   File "/opt/conda/lib/python3.7/threading.py", line 300, in wait
#     gotit = waiter.acquire(True, timeout)
#   File "/opt/conda/lib/python3.7/site-packages/torch/utils/data/dataloader.py", line 274, in handler
#     _error_if_any_worker_fails()
# RuntimeError: DataLoader worker (pid 21103) is killed by signal: Bus error.`


There is no good workaround here: starting with small fast minibatches compromises final quality, while starting with big slow minibatches may work but then costs far more compute. I did find that the G/D accumulations can be imbalanced to allow increasing the G’s total minibatch (which appears to be the key for better quality) but then this risks destabilizing training. These bugs need to be fixed before trying BigGAN for real.


### BigGAN: ImageNet → Danbooru2018-1K


In any case, I ran the 128px ImageNet → Danbooru2018-1K for ~6 GPU-days (or ~3 days on my 2×1080ti workstation) and the training montage indicates it was working fine:

    Training montage of the 128px ImageNet → Danbooru2018-1K; successful


Sometime after that, while continuing to play with imbalanced minibatches to avoid triggering the iteration/crash bugs, it diverged badly and mode-collapsed into static, so I killed the run, as the point appears to have been made: transfer learning is indeed possible, and the speed of the adaptation suggests benefits to training time by starting with a highly-trained model already.


### BigGAN: 256px Danbooru2018-1K


More seriously, I began training a 256px model on Danbooru2018-1K portraits. This required rebuilding the HDF5 with 256px settings, and since I wasn’t doing transfer learning, I used the BigGAN-deep architecture settings since that has better results & is smaller than the original BigGAN.


My own 2×1080ti were inadequate for reasonable turnaround on training a 256px BigGAN from scratch—they would take something like 4+ months wallclock— so I decided to shell out for a big cloud instance. AWS/GCP are too expensive, so I used this to investigate Vast.ai as an alternative: they typically have much lower prices.


Vast.ai setup was straightforward, and I found a nice instance: an 8×2080ti machine available for just $2.17$1.72019/hour (AWS, for comparison, would charge closer to $2.76$2.162019/hour for just 8 K80 halves). So I ran 2019-05-02–2019-06-03 their 8×2080ti instance ($2.17$1.72019/hour; total: $1,752.45$1,373.642019).


That is ~250 GPU-days of training, although this is a misleading way to put it since the Vast.ai bill includes bandwidth/hard-drive in that total and the GPU utilization was poor so each ‘GPU-day’ is worth about a third less than with the 128px BigGAN which had good GPU utilization and the 2080tis were overkill. It should be possible to do much better with the same budget in the future.


The training command:


`python train.py --model BigGANdeep --dataset D1K_hdf5 --parallel --shuffle --num_workers 16 \
    --batch_size 56 --num_G_accumulations 8 --num_D_accumulations 8 --num_D_steps 1 --G_lr 1e-4 \
    --D_lr 4e-4 --D_B2 0.999 --G_B2 0.999 --G_attn 64 --D_attn 64 --G_ch 128 --D_ch 128 \
    --G_depth 2 --D_depth 2 --G_nl inplace_relu --D_nl inplace_relu --SN_eps 1e-6 --BN_eps 1e-5 \
    --adam_eps 1e-6 --G_ortho 0.0 --G_shared --G_init ortho --D_init ortho --hier --dim_z 64 \
    --shared_dim 64 --ema --use_ema --G_eval_mode --test_every 200000 --sv_log_interval 1000 \
    --save_every 90 --num_best_copies 1 --num_save_copies 1 --seed 0 --no_fid \
    --num_inception_images 1 --augment --data_root ~/tmp --resume --experiment_name \
    BigGAN_D1K_hdf5_BigGANdeep_seed0_Gch128_Dch128_Gd2_Dd2_bs64_Glr1.0e-04_Dlr4.0e-04_Gnlinplace_relu_Dnlinplace_relu_Ginitortho_Dinitortho_Gattn64_Dattn64_Gshared_hier_ema`


The system worked well but BigGAN turns out to have serious performance bottlenecks (apparently in synchronizing batchnorm across GPUs) and did not make good use of the 8 GPUs, averaging GPU utilization ~30% according to `nvidia-smi`. (On my 2×1080tis with the 128px, GPU-utilization was closer to 95%.) In retrospect, I probably should’ve switched to a less expensive instance like a 8×1080ti where it likely would’ve had similar throughput but cost less.


Training progressed well up until iterations #80–90k, when I began seeing signs of mode collapse:

    Training montage of the 256px Danbooru2018-1K; semi-successful (note when EMA begins to be used for sampling images at ~8s, and the mode collapse at the end)


I was unable to increase the minibatch to more than ~500 because of the bugs, limiting what I could do against mode collapse, and I suspect the small minibatch was why mode collapse was happening in the first place. (Gokaslan tried the last checkpoint I saved—#95,160—with the same settings, and ran it to #100,000 iterations and experienced near-total mode collapse.)


The last checkpoint I saved from before mode collapse was #83,520, saved on 2019-05-28 after ~24 wallclock days (accounting for various crashes & time setting up & tweaking).


Random samples, interpolation grids (not videos), and class-conditional samples can be generated using `sample.py`; like `train.py`, it requires the exact architecture to be specified. I used the following command (many of the options are probably not necessary, but I didn’t know which):


`python sample.py --model BigGANdeep --dataset D1K_hdf5 --parallel --shuffle --num_workers 16 \
    --batch_size 56 --num_G_accumulations 8 --num_D_accumulations 8 --num_D_steps 1 \
    --G_lr 1e-4 --D_lr 4e-4 --D_B2 0.999 --G_B2 0.999 --G_attn 64 --D_attn 64 --G_ch 128 \
    --D_ch 128 --G_depth 2 --D_depth 2 --G_nl inplace_relu --D_nl inplace_relu --SN_eps 1e-6 \
    --BN_eps 1e-5 --adam_eps 1e-6 --G_ortho 0.0 --G_shared --G_init ortho --D_init ortho --hier \
    --dim_z 64 --shared_dim 64 --ema --use_ema --G_eval_mode --test_every 200000 \
    --sv_log_interval 1000 --save_every 90 --num_best_copies 1 --num_save_copies 1 --seed 0 \
    --no_fid --num_inception_images 1 --skip_init --G_batch_size 32 --use_ema --G_eval_mode \
    --sample_random --sample_sheets --sample_interps --resume --experiment_name 256px`


Random samples are already well-represented by the training montage. The interpolations look similar to StyleGAN interpolations. The class-conditional samples are the most fun to look at because one can look at specific characters without the need to retrain the entire model, which while only taking a few hours at most, is a hassle.

#### 256px Danbooru2018-1K Samples


Interpolation images and 5 character-specific random samples (Asuka, Holo, Rin, Chen, Ruri) for our 256px BigGAN trained on 1,000 characters from Danbooru2018:


Random interpolation samples (256px BigGAN trained on 1,000 Danbooru2018 character portraits)


Souryuu Asuka Langley (Neon Genesis Evangelion), class #825 random samples


Holo (Spice and Wolf), class #273 random samples


Rin Tohsaka (Fate/Stay Night), class #891


Yakumo Chen (Touhou), class #123 random samples


Ruri Hoshino (Martian Successor Nadesico), class #286 random samples


#### 256px BigGAN Downloads


Model & sample downloads:

- 

trained model: `2019-05-28-biggan-danbooru2018-snapshot-83520.tar.xz` (291MB)
- 

random samples for all 1,000 character classes (321MB)


#### Evaluation


Sarcastic commentary on BigGAN quality by /u/Klockbox


The best results from the 128px BigGAN model look about as good as could be expected from 128px samples; the 256px model is fairly good, but suffers from much more noticeable artifacting than 512px StyleGAN, and cost $1,751.63$1,3732019 (a 256px StyleGAN would have been closer to $510.31$4002019 on AWS). In BigGAN’s defense, it had clearly not converged yet and could have benefited from much more training and much larger minibatches, had that been possible. Qualitatively, looking at the more complex elements of samples, like hair ornaments/hats, I feel like BigGAN was doing a much better job of coping with complexity & fine detail than StyleGAN would have at a similar point.


However, training 512px portraits or whole-Danbooru images is infeasible at this point: while the cost might be only a few thousand dollars, the various bugs mean that it may not be possible to stably train to a useful quality. It’s a dilemma: at small or easy domains, StyleGAN is much faster (if not better); but at large or hard domains, mode collapse is too risky and endangers the big investment necessary to surpass StyleGAN.


To make BigGAN viable, it needs at least:

- 

minibatch size bugs fixed to enable up to n = 2,048 (or larger, as gradient noise scale indicates)
- 

512px architectures defined, to allow transfer learning from the released Tensorflow 512px ImageNet model
- 

optimization work to reduce overhead and allow reasonable GPU utilization on >2-GPU systems


With those done, it should be possible to train 512px portraits for <$1,275.77$1,0002019 and whole-Danbooru images for <$12,757.68$10,0002019. (Given the release of DeepDanbooru as a TensorFlow model, enabling an anime-specific perceptual loss, it would also be interesting to investigate applying “NoGAN” pretraining to BigGAN.)


## Compare_gan


### Danbooru2019+e621 256px BigGAN


Release of a 256px BigGAN model trained on Danbooru2019 & e621. This is a prototype model testing our ability to train a BigGAN stably for hundreds of thousands of iterations on a TPU-256 pod on 3 million+ anime/illustration images. While the generated samples are far from ‘photorealistic’, they serve as proof of concept that—unlike our failed StyleGAN2 scaling experiments—BigGAN can successfully model anime images with great generality, and that we can potentially scale up to 512px or even 1024px and match the DeepMind ImageNet BigGAN for quality.


As part of testing our modifications to `compare_gan`, including sampling from multiple datasets to increase n and using flood loss to stabilize it and adding an additional (crude, limited) kind of self-supervised SimCLR loss to the D, we trained several 256px BigGANs, initially on Danbooru2019 SFW but then adding in the TWDNE portraits & e621/e621-portraits partway through training. This destabilized the models greatly, but the flood loss appears to have stopped divergence and they gradually recovered. Run ‘too good’. Freezing models is an old GAN trick which is mostly not used post-WGAN, but appears useful for BigGAN, perhaps because of the spiky loss curve, especially early in training. (The quality of later BigGAN runs as much higher. We only discovered much later in 2020 that the compare_gan default behavior of resizing images to 256px by ‘random cropping’ was seriously destabilizing for both BigGAN & StyleGAN compared to ‘top cropping’, and only in 2021 did Shawn Presser discover what seems to be the fatal flaw of compare_gan’s implementation: an innocent-seeming omission of a ‘+1’ in the gamma parameter of an image processing step.)


We ran it for 607,250 iterations on a TPUv3-256 pod until 2020-05-15. Config:


`{"dataset.name": "images_256", "resnet_biggan.Discriminator.blocks_with_attention": "B2",
"resnet_biggan.Discriminator.ch": 96, "resnet_biggan.Generator.blocks_with_attention": "B5",
"resnet_biggan.Generator.ch": 96, "resnet_biggan.Generator.plain_tanh": false, "ModularGAN.d_lr": 0.0005,
"ModularGAN.d_lr_mul": 3.0, "ModularGAN.ema_start_step": 4000, "ModularGAN.g_lr": 6.66e-05,
"ModularGAN.g_lr_mul": 1.0, "options.batch_size": 2048, "options.d_flood": 0.2,
"options.datasets": "gs://XYZ-euw4a/datasets/danbooru2019-s/danbooru2019-s-0*,gs://XYZ-euw4a/datasets/e621-s/e621-s-0*,
    gs://XYZ-euw4a/datasets/portraits/portraits-0*,gs://XYZ-euw4a/datasets/e621-portraits-s-512/e621-portraits-s-512-0*",
"options.g_flood": 0.05, "options.labels": "", "options.random_labels": true, "options.z_dim": 140,
"run_config.experimental_host_call_every_n_steps": 50, "run_config.keep_checkpoint_every_n_hours": 0.5,
"standardize_batch.use_cross_replica_mean": true, "TpuSummaries.save_image_steps": 50, "TpuSummaries.save_summary_steps": 1}`


90 random EMA samples (untruncated) from the 256px BigGAN trained on Danbooru2019/anime-portraits/e621/e621-portraits.


    Interpolation using HighCWu PaddlePaddle Google Colab notebook


The model is available for download:


`rsync --verbose rsync://176.9.41.242:873/biggan/2020-05-18-spresser-biggan-256px-danbooruplus-run39-607250.tar.xz ./`


`compare_gan` config:


`$ cat bigrun39b/operative_config-603500.gin
# Parameters for AdamOptimizer:
AdamOptimizer.beta1 = 0.0
AdamOptimizer.beta2 = 0.999
AdamOptimizer.epsilon = 1e-08
AdamOptimizer.use_locking = False

# Parameters for batch_norm:
# None.

# Parameters for BigGanResNetBlock:
BigGanResNetBlock.add_shortcut = True

# Parameters for conditional_batch_norm:
conditional_batch_norm.use_bias = False

# Parameters for cross_replica_moments:
cross_replica_moments.group_size = None
cross_replica_moments.parallel = True

# Parameters for D:
D.batch_norm_fn = None
D.layer_norm = False
D.spectral_norm = True

# Parameters for dataset:
dataset.name = 'images_256'
dataset.seed = 547

# Parameters for resnet_biggan.Discriminator:
resnet_biggan.Discriminator.blocks_with_attention = 'B2'
resnet_biggan.Discriminator.ch = 96
resnet_biggan.Discriminator.channel_multipliers = None
resnet_biggan.Discriminator.project_y = True

# Parameters for G:
G.batch_norm_fn = @conditional_batch_norm
G.spectral_norm = True

# Parameters for resnet_biggan.Generator:
resnet_biggan.Generator.blocks_with_attention = 'B5'
resnet_biggan.Generator.ch = 96
resnet_biggan.Generator.channel_multipliers = None
resnet_biggan.Generator.embed_bias = False
resnet_biggan.Generator.embed_y = True
resnet_biggan.Generator.embed_y_dim = 128
resnet_biggan.Generator.embed_z = False
resnet_biggan.Generator.hierarchical_z = True
resnet_biggan.Generator.plain_tanh = False

# Parameters for hinge:
# None.

# Parameters for loss:
loss.fn = @hinge

# Parameters for ModularGAN:
ModularGAN.conditional = True
ModularGAN.d_lr = 0.0005
ModularGAN.d_lr_mul = 3.0
ModularGAN.d_optimizer_fn = @tf.train.AdamOptimizer
ModularGAN.deprecated_split_disc_calls = False
ModularGAN.ema_decay = 0.9999
ModularGAN.ema_start_step = 4000
ModularGAN.experimental_force_graph_unroll = False
ModularGAN.experimental_joint_gen_for_disc = False
ModularGAN.fit_label_distribution = False
ModularGAN.g_lr = 6.66e-05
ModularGAN.g_lr_mul = 1.0
ModularGAN.g_optimizer_fn = @tf.train.AdamOptimizer
ModularGAN.g_use_ema = True

# Parameters for no_penalty:
# None.

# Parameters for normal:
normal.mean = 0.0
normal.seed = None

# Parameters for options:
options.architecture = 'resnet_biggan_arch'
options.batch_size = 2048
options.d_flood = 0.2
options.datasets = \
    'gs://darnbooru-euw4a/datasets/danbooru2019-s/danbooru2019-s-0*,gs://darnbooru-euw4a/datasets/e621-s/e621-s-0*,gs://darnbooru-euw4a/datasets/portraits/portraits-0*,gs://darnbooru-euw4a/datasets/e621-portraits-s-512/e621-portraits-s-512-0*'
options.description = \
    'Describe your GIN config. (This appears in the tensorboard text tab.)'
options.disc_iters = 2
options.discriminator_normalization = None
options.g_flood = 0.05
options.gan_class = @ModularGAN
options.image_grid_height = 3
options.image_grid_resolution = 1024
options.image_grid_width = 3
options.labels = ''
options.lamba = 1
options.model_dir = 'gs://darnbooru-euw4a/runs/bigrun39b/'
options.num_classes = 1000
options.random_labels = True
options.training_steps = 250000
options.transpose_input = False
options.z_dim = 140

# Parameters for penalty:
penalty.fn = @no_penalty

# Parameters for replace_labels:
replace_labels.file_pattern = None

# Parameters for run_config:
run_config.experimental_host_call_every_n_steps = 50
run_config.iterations_per_loop = 250
run_config.keep_checkpoint_every_n_hours = 0.5
run_config.keep_checkpoint_max = 10
run_config.save_checkpoints_steps = 250
run_config.single_core = False
run_config.tf_random_seed = None

# Parameters for spectral_norm:
spectral_norm.epsilon = 1e-12
spectral_norm.singular_value = 'auto'

# Parameters for standardize_batch:
standardize_batch.decay = 0.9
standardize_batch.epsilon = 1e-05
standardize_batch.use_cross_replica_mean = True
standardize_batch.use_moving_averages = False

# Parameters for TpuSummaries:
TpuSummaries.save_image_steps = 50
TpuSummaries.save_summary_steps = 1

# Parameters for train_imagenet_transform:
train_imagenet_transform.crop_method = 'random'

# Parameters for weights:
weights.initializer = 'orthogonal'

# Parameters for z:
z.distribution_fn = @tf.random.normal
z.maxval = 1.0
z.minval = -1.0
z.stddev = 1.0`


- 

ImageNet requires you to sign up & be approved to download from them, but 2 months later I had heard nothing back (and still have not as of January 2021). So I used the data from `ILSVRC2012_img_train.tar` (MD5: `1d675b47d978889d74fa0da5fadfb00e`; 138GB) which I downloaded from the ImageNet LSVRC 201214ya Training Set (Object Detection) torrent.↩︎
- 

Danbooru can classify the same character under multiple tags: for example, Sailor Moon characters are tagged under their “Sailor X” name for images of their transformed version, and their real names for ‘civilian’ images (eg. ‘Sailor Venus’ or ‘Cure Moonlight’, the former of which I merged with ‘Aino Minako’). Some popular franchises have many variants of each character: the Fate franchise, especially with the success of Fate/Grand Order, is a particular offender, with quite a few variants of characters like Saber.↩︎
- 

One would think it would, but I asked Brock and apparently it doesn’t help to occasionally initialize from the EMA snapshots. EMA is a mysterious thing.↩︎
- 

As far as I can tell, it has something to do with the `dataloader` code in `utils.py`: the calculation of length and the iterator do something weird to adjust for previous training, so the net effect is that you can run with a fixed minibatch accumulation and it’ll be fine, and you can reduce the number of accumulations, and it’ll simply underrun the dataloader, but if you increase the number of accumulations, if you’ve trained enough percentage-wise, it’ll immediately flip over into a negative length and indexing into it becomes completely impossible, leading to crashes. Unfortunately, I only ever want to increase the minibatch accumulation… I tried to fix it but the logic is too convoluted for me to follow it.↩︎



Error: JavaScript disabled.

Backlinks, similar links, and the bibliography require JS enabled to load.
        # Backlinks


        [Backlinks (what links here)]
        # Similar Links


        [Similar links by topic]
        # Bibliography

 ' is redundant with the ''; but added to parallel Pandoc-generated headers which set all attributes/classes on both. -->
        [Bibliography of links/references used in page]




        [&hairsp;Send Anonymous Feedback&hairsp;]

[Quote Of The Day]

[Site Of The Day]

[Annotation Of The Day]

[adblock public service announcement]

      ​
