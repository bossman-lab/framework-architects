# “How Many Shower Controls Are There?”, by Gwern, GPT-5.2 Pro

[Source](https://gwern.net/shower-controls)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # How Many Shower Controls Are There?





R (language), design, Fermi problems, ABC Bayes, mark-and-recapture

Answer: Too many! After observing 14 unique shower controls across 20 stays while traveling, I used capture-recapture statistics to estimate the total population of designs, finding a likely mean of >34 types but a wide credible interval because I recorded the wrong kind of recapture data. Ultimately, the exercise served as a demonstration of R. A. Fisher’s warning that statistical analysis is too often a ‘post mortem’ that cannot rescue a flawed experimental design.
            by: Gwern, GPT-5.2 Pro
            2023-07-31–2026-01-15
            finished
            certainty: highly likely
            importance: 3
            similar
            bibliography

- Unseen Species Problem
- Data
- Approximation: Birthday Problem
- Capture-Recapture

- Chao2
- ABC Bayes

- Post Mortem
- External Links

While traveling on the West/East Coast in 2024–2025, I was repeatedly frustrated by how each place I stayed had a different shower control. I would get to my new place, sometimes bedraggled, and then have to experiment with each badly designed new shower, lest I be frozen or blanched by the downpour.


After the 4th time this happened, I started to become puzzled rather than frustrated: why weren’t they repeating? How could there be this many ways to design something as simple as a 2×2 matrix—cold vs hot, little vs lot? More concerningly, if I still hadn’t hit any ‘repeats’, that implied that there was a large ‘population’ of shower controls, so many that I could sample 4 in a row without seeing any twice or more times; just how many shower controls are there in coastal US hotels?


A simple, common shower control, of the sort I know how to use.


An especially baroque shower control which feels more like a mechanical puzzle than a control.


An egregious shower, which controls requires an adjustment hidden behind the shower head.


# Unseen Species Problem


I realized that this was an answerable question, because it was a familiar statistical problem in different guise: it is the unseen species estimation problem, or capture-recapture analysis (a famous instance of which is the German tank problem), and we could also treat it as a birthday problem paradox (along the lines of ‘how big a party of shower controls do we need for a pair to probably collide?’).


Unfortunately, you can’t really estimate anything from no-repeats. A run of uniques is almost equally consistent with every possible ‘large’ population, and provides minimal evidence about the population: I would see 4 uniques almost every time if the population were 100, 100 million, or 100 trillion.


From a maximum likelihood estimation perspective, this is ill-defined, as you can always slightly increase the ‘likelihood’ of the observation by postulating an even larger population, and the highest likelihood would be assuming a population of size ∞ (as then you would always observe 4 uniques, as opposed to just 99.99…% of the time). Enforcing a Bayesian prior, like a log-normal distribution on the shower population, with a plausible mean like 100, would tame this and let us slightly adjust our posterior away from smaller populations like 4–100, and towards 100–∞, but only a little, and no one else would find this exercise interesting.


So you have to wait for a repeat before you analyze anything.


I assumed this would happen quickly, and began noting on Twitter in 2024 how I kept hitting unique shower controls.


# Data


It actually took until mid-2025, at the 12th place, before I finally hit the first repeat, and I could begin estimating from 11⁄12 uniques. By the end of 2025, I had observed 14⁄20 unique shower controls.


# Approximation: Birthday Problem


So, the simplest heuristic would be the birthday problem: we expect to have √(π·N⁄2) showers at the first collision, so what N makes that equal to 12? Squaring: 144 ≈ π·N⧸2; N ≈ 288⧸π ≈ 288⧸3.14159 ≈ 92.


But this throws away much of the information I got later on, when I ended with 14⁄20 uniques; so our 92 estimate can be improved. Further, the birthday paradox & coupon collecting problems usually assume each kind is equally likely, although with shower controls, we would expect some sort of long tail of discontinued models or weird one-offs.


# Capture-Recapture


## Chao2


To estimate the actual number of shower controls, you need to estimate how much probability mass is sitting in undetected rare controls. There could be 1 kind of popular shower control, and then 10,000 unique one-offs—how would we ever know if we just tracked ‘time to first collision’?


Just counting uniques is not enough. The information about that mass of possible rare kinds lives almost entirely in the rare end of the frequency table: how many controls you saw exactly once (“singletons”) versus exactly twice (“doubletons”).


Chao’s lower-bound approach (“Chao2”) makes this explicit via a Cauchy-Schwarz inequality that turns the singleton/doubleton counts into a minimum estimate of the unseen remainder (Chao & Colwell 2017).


Let T be the number of stays (here T = 20). Let Sobs be the number of distinct controls observed (here Sobs = 14). Let Q1 be the number of controls seen in exactly one stay, and Q2 the number seen in exactly two stays.


Then the classic Chao2 lower bound is:


ŜChao2 := Sobs + (T − 1)⧸T × Q12⧸(2· Q2)


This immediately shows why “14⁄20 unique” is not enough by itself.


Those same totals can come from very different frequency tables, and Chao2 reacts very differently.


If the 6 repeat-observations are spread out (6 different controls each seen twice), then (Q1 = 8, Q2 = 6), and Chao2 lands around ~19 total controls.


If instead one control is common and everything else is a singleton ((Q1 = 13, Q2 = 0)), then the bias-corrected Chao2-style lower bound jumps to ~88 controls.


## ABC Bayes


If I want a tidy point estimate anyway, I have to buy it by making the tail assumptions explicit.


That means writing down a prior over the total number of controls and a model for how unequal their probabilities are (for example, treating per-control frequencies as a normalized discrete log-normal), then simulating and conditioning on summaries (ie. Sobs, Q1, Q2)


We can do this quickly with ABC. We implement ABC rejection sampling for the number of types c with the simplest possible prior of a discrete uniform on [cmin, cmax]; somewhat arbitrarily, I’ll pick 100 as the maximum. The generative likelihood simulator is just uniform types 1…c (equi-probable). In R (math & code primarily written by GPT-5.2 Pro, with feedback from Claude-4.5-opus, Gemini-3-pro-preview, and DeepSeek-v3):


`simulate_uniform_types <- function(c, n) {
  stopifnot(c >= 1L, n >= 1L)
  sample.int(c, size = n, replace = TRUE)
}

summarize_draws <- function(draws) {
  tab <- table(draws)
  counts <- as.integer(tab)

  K  <- length(counts)    # number of distinct types observed
  Q1 <- sum(counts == 1L) # number of singletons
  Q2 <- sum(counts == 2L) # number of doubletons

  dup_idx <- which(duplicated(draws))
  Tfirst <- if (length(dup_idx) == 0L) Inf else dup_idx[1L] # first repeat index

  c(K = K, Q1 = Q1, Q2 = Q2, Tfirst = Tfirst)
}

absdiff <- function(a, b) {
  if (is.infinite(a) && is.infinite(b)) return(0)
  if (is.infinite(a) != is.infinite(b)) return(Inf)
  abs(a - b)
}

abc_distance <- function(sim_stats, obs_stats, weights = NULL) {
  stopifnot(all(names(obs_stats) %in% names(sim_stats)))

  use <- !is.na(obs_stats)
  s <- sim_stats[names(obs_stats)][use]
  o <- obs_stats[use]

  if (is.null(weights)) {
    w <- rep(1, length(o))
  } else {
    w <- weights[names(obs_stats)][use]
    w[is.na(w)] <- 1
  }

  sum(w * mapply(absdiff, s, o))
}

abc_rejection_c_uniform <- function(
  n_accept = 2000L,
  _n_ = 20L,
  obs_stats = c(K = 14, Q1 = NA, Q2 = NA, Tfirst = NA),
  eps = 0,
  c_min = 1L,
  c_max = 100L,
  max_trials = 5e6,
  weights = c(K = 1, Q1 = 1, Q2 = 1, Tfirst = 1),
  seed = NULL
) {
  if (!is.null(seed)) set.seed(seed)

  stopifnot(n_accept >= 1L, n >= 1L, eps >= 0)
  stopifnot(c_min >= 1L, c_max >= c_min)

  # Enforce c >= observed K if K is provided.
  c_low <- c_min
  if (!is.na(obs_stats["K"])) c_low <- max(c_low, as.integer(obs_stats["K"]))

  if (c_low > c_max) stop("No support: c_max < observed K (or c_min).")

  accepted <- data.frame(
    c = integer(0),
    K = integer(0),
    Q1 = integer(0),
    Q2 = integer(0),
    Tfirst = numeric(0),
    stringsAsFactors = FALSE
  )

  trials <- 0L
  while (nrow(accepted) < n_accept && trials < max_trials) {
    trials <- trials + 1L

    # discrete uniform prior on [c_low, c_max]; see also birthday paradox discussion
    c_candidate <- sample.int(c_max - c_low + 1L, 1L) + c_low - 1L

    draws <- simulate_uniform_types(c_candidate, n)
    sim_stats <- summarize_draws(draws)

    d <- abc_distance(sim_stats, obs_stats, weights = weights)
    if (d <= eps) {
      # WARNING: rbind is notoriously slow and 'accidentally quadratic' in a loop like this;
      # a real implementation would vectorize to use pre-allocated vectors & subset afterwards.
      accepted <- rbind(
        accepted,
        data.frame(
          c = c_candidate,
          K = sim_stats["K"],
          Q1 = sim_stats["Q1"],
          Q2 = sim_stats["Q2"],
          Tfirst = sim_stats["Tfirst"],
          stringsAsFactors = FALSE
        )
      )
    }
  }

  if (nrow(accepted) < n_accept) {
    warning(sprintf(
      "Stopped early: accepted %d / %d after %d trials (try larger eps, fewer stats, or bigger max_trials).",
      nrow(accepted), n_accept, trials
    ))
  }

  list(
    accepted = accepted,
    trials = trials,
    accept_rate = nrow(accepted) / trials
  )
}`


Example usage:


`## Only condition on K = 14 out of 𝑛 = 20 (exact match on K):
res_K <- abc_rejection_c_uniform(
  n_accept = 5000,
  _n_ = 20,
  obs_stats = c(K = 14, Q1 = NA, Q2 = NA, Tfirst = NA),
  eps = 0,
  c_min = 1, c_max = 100,
  seed = 1
)

summary(res_K$accepted$c); quantile(res_K$accepted$c, c(0.025, 0.5, 0.975))
# Min. 1st Qu.  Median    Mean 3rd Qu.    Max.
#  14.000  24.000  30.000  33.921  40.000 100.000
#  2.5%   50% 97.5%
#    18    30    72`


So we have a mean estimate of 34 shower control types, with a wide 95% credible interval of 18–72.


If we also want to condition on first repeat at draw 12, since first repeat really occurred at the 12th stay overall, we can simply add that to the acceptance requirements. Does this add meaningful information and sharpen our posterior?


No, perhaps a little surprisingly, as our results are near-identical:


`res_K_Tfirst <- abc_rejection_c_uniform(
  n_accept = 50000,
  _n_ = 20,
  obs_stats = c(K = 14, Q1 = NA, Q2 = NA, Tfirst = 12),
  eps = 0,
  c_min = 1, c_max = 100,
  seed = 1
)

summary(res_K_Tfirst$accepted$c); quantile(res_K_Tfirst$accepted$c, c(0.025, 0.5, 0.975))
# Min.  1st Qu.   Median     Mean  3rd Qu.     Max.
#  14.0000  24.0000  30.0000  33.9098  40.0000 100.0000
#  2.5%   50% 97.5%
#    17    30    72`


Apparently observing our first duplicate or Tfirst = 12 is highly ordinary for our final summary observation, and so tells us nothing; indeed, in the uniform model, after we know k = 14, it tells us nothing further, and so our sufficient statistic is just the overall (k = 14, n = 20).


We can also try to compute the exact likelihood for “K = k distinct types in n draws given c” and compare it to ABC when `eps` = 0 and we only condition on K:


`# occupancy / Stirling number: <https://statistics.berkeley.edu/sites/default/files/tech-reports/452.pdf>
stirling2_table <- function(n_max) {
  S <- matrix(0, nrow = n_max + 1L, ncol = n_max + 1L)
  S[1L, 1L] <- 1 # S(0,0)=1
  for (n in 1L:n_max) {
    for (k in 1L:n) {
      S[n+1L, k+1L] <- k * S[n, k+1L] + S[n, k]
    }
  }
  S
}

log_falling_factorial <- function(c, k) {
  sum(log(c - (0:(k-1L))))
}

posterior_exact_c_given_K_unifprior <- function(_n_ = 20L, k = 14L, c_min = 1L, c_max = 100L) {
  stopifnot(1L <= k, k <= n, c_min >= 1L, c_max >= c_min)

  c_vals <- c_min:c_max
  prior <- rep(1 / length(c_vals), length(c_vals))
  prior[c_vals < k] <- 0
  prior <- prior / sum(prior)

  S <- stirling2_table(n)
  S_nk <- S[n+1L, k+1L]

  loglik <- rep(-Inf, length(c_vals))
  ok <- which(c_vals >= k)
  loglik[ok] <- log(S_nk) + vapply(c_vals[ok], log_falling_factorial, numeric(1), k = k) - n * log(c_vals[ok])

  logpost <- log(prior) + loglik
  logpost <- logpost - max(logpost)
  post <- exp(logpost)
  post <- post / sum(post)

  data.frame(c = c_vals, posterior = post)
}

post <- posterior_exact_c_given_K_unifprior(_n_ = 20, k = 14, c_min = 1, c_max = 100)
with(post, c[which.max(posterior)]) # MAP
# [1] 25
with(post, sum(c * posterior))      # mean
# [1] 33.9531824`


Which replicates our previous posterior mean estimate of 34. This further implies that right now, I have a ~50% chance of seeing a new shower control at each new place and with 10 more stays, would see ~5 (1–8) new shower controls:


`k <- 14
m <- 10

## 1. Probability the NEXT (21st) stay is a new control
## (WARNING: only under equi-probability)
## Formula given c: (c − k) ⧸ c
prob_next_new_given_c <- (post$c - k) / post$c

## Marginalize: Sum( P(new|c) * P(c|data) )
posterior_prob_next_new <- sum(prob_next_new_given_c * post$posterior)

## 2. Expected number of new controls in the next 10 stays
## Formula given c: (Unseen) ⋅ (Probability of finding a specific unseen in 10 tries)
m <- 10
unseen_given_c <- post$c - k
prob_finding_specific_unseen <- 1 - (1 - 1/post$c)^m

expected_new_given_c <- unseen_given_c * prob_finding_specific_unseen

## Marginalize
posterior_expected_new_10 <- sum(expected_new_given_c * post$posterior)

cat(sprintf("Probability next stay is new: %.3f\n", posterior_prob_next_new))
# Probability next stay is new: 0.528
cat(sprintf("Expected new in next 10: %.3f\n", posterior_expected_new_10))
# Expected new in next 10: 4.626

## credible intervals:
wquantile <- function(x, w, probs) {
  o <- order(x)
  x <- x[o]; w <- w[o]
  cw <- cumsum(w) / sum(w)
  sapply(probs, function(p) x[which(cw >= p)[1]])
}

p_next_new_given_c <- (post$c - k) / post$c
e_new_m_given_c    <- (post$c - k) * (1 - (1 - 1/post$c)^m)

wquantile(p_next_new_given_c, post$posterior, c(.025,.5,.975))
# [1] 0.176470588 0.533333333 0.805555556
wquantile(e_new_m_given_c,    post$posterior, c(.025,.5,.975))
# [1] 1.36381703 4.60045770 7.57028469`


And if we wanted to extend the simulation to include heterogeneity and avoid the naive equal-probability assumption, we could try to treat the long tail as a Dirichlet-multinomial distribution where small α gives heavy skew (approaching our original uniform as we make α larger). Then put a prior on α and marginalize. Something like:


`rsimulate_dirichlet_types <- function(c, n, alpha = 1) {
  probs <- rgamma(c, shape = alpha, rate = 1)
  probs <- probs / sum(probs)
  sample.int(c, size = n, replace = TRUE, prob = probs)
}`


Then do ABC jointly over (c, α). This will give us higher but more realistic posterior mean estimates. However, I will skip that because our results are already so weak, and I don’t have strong prior intuitions for how a α hyperparameter should be distributed.


# Post Mortem


Overall, it seems that broadly speaking across the various approaches, we can be quite sure that there’s >20 shower controls and I can expect to see more in the future. And there’s a good chance we could see a large number, possibly >100, given the underestimate bias.


And unfortunately, we can’t be more precise because I turned out to have recorded insufficient statistics; what I really needed to do is photograph & document each one, so I knew how many times I had observed each kind.


Oops. I guess I should have done an analysis before all the traveling, to know what data I needed to collect… Too late now; to quote R. A. Fisher (who happened to work on this problem as well):


The statistician is no longer an alchemist expected to produce gold from any worthless material offered him. He is more like a chemist capable of assaying exactly how much of value it contains, and capable also of extracting this amount, and no more. In these circumstances, it would be foolish to commend a statistician because his results are precise, or to reprove because they are not. If he is competent in his craft, the value of the result follows solely from the value of the material given him. It contains so much information and no more. His job is only to produce what it contains…Immensely laborious calculations on inferior data may increase the yield 95 → 100%. A gain of 5%, of perhaps a small total. A competent overhauling of the process of collection, or of the experimental design, may often increase the yield 10 or 12×, for the same cost in time and labour.


…To consult the statistician after an experiment is finished is often merely to ask him to conduct a post mortem examination. He can perhaps say what the experiment died of.


—R. A. Fisher, “Presidential address to the first Indian statistical congress”, 1938


So overall, our observations are not that statistically informative and can’t tell us how many shower controls there are beyond “a lot more than I originally expected”.


# External Links


- 

Discussion: Marginal Revolution



Error: JavaScript disabled.

Backlinks, similar links, and the bibliography require JS enabled to load.
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
