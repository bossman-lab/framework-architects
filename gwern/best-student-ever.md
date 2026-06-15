# Best Student Ever!

[Source](https://gwern.net/best-student-ever)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Best Student Ever!





order statistics

Harold Bloom amusingly recommends all students as his ‘best student ever’; modeled as a ‘record value’ order statistics problem, this is more common than it seems.
            2023-08-27–2025-03-22
            finished
            certainty: certain
            importance: 2
            similar

- Record Value Problem

- Doubling Interval
- Harmonic Series



How often could a teacher truthfully say of a student, such as in a letter of recommendation, that the student was their “best student ever”?


This is an instance of the ‘record value’ problem in order statistics, and can be easily solved if we know how many students are taught each year:


there are surprisingly many record-values, because the number of best-evers will grow roughly logarithmically in total students, as the initial burst of record-setters fades out into ever-rarer record-breakers.


For example, for the literary critic Harold Bloom’s 64-year-long teaching career, he might observe something like ln(6,400) ≈ 9 best-ever students.


A 2002 New Yorker profile of the late literary critic Harold Bloom included, among its amusing anecdotes, a parenthetical observation about letters of recommendation:


Harold Bloom is indeed alienated from his entire profession. He has given up teaching graduate students because, he says, he fears that they will be tarred by his brush. (The value of his support has also been somewhat downgraded by his habit of scrawling genially, on recommendations, “Best student I ever had.”)


This is amusing, of course, because how could they all be his best student? Surely “there can only be one”?


And that is true, but on further thought, that’s not quite the same thing as what his letters are claiming—a teacher might truthfully be able to say of multiple students that they were “the best student I ever had [yet]”, because a future student might be better. Unless he has just retired and will have no more students, how can he know he won’t get a better student? Indeed, a teacher might regularly get a best-yet student, particularly if they started with small classes and worked their way up to large classes, or they started at the worst schools and got reassigned to better schools, or any number of things. (We could imagine the extreme case where a teacher with n students truthfully observes n best-yet students—because they somehow arrived in exact rank-order, worst-first. For small n, this worst-case sorting wouldn’t even be all that improbable by chance.)


How many best-thus-far students might there be for a teacher, where they could honestly write such a recommendation?

# Record Value Problem


This is a version of the record value question: asking how many times a record will be broken, given the passage of time or number of attempts or population etc. (There are also solutions for the case where we don’t know how many ‘attempts’ there are, but they get harder.)


Bloom taught at Yale for a remarkably long time: 1955–642019, or 64 years (just 4 days before his death!). As a cantankerous world-famous tenured professor who wrote prolifically, it seems safe to say that his teaching load could not have been too extreme, and he would not have allowed the class sizes to increase much over time (if only because his teaching didn’t get any more efficient over time). If we imagine perhaps 3 classes of 33 students a year or 100 a year, he would then have 6,400 students total. With that many students, how many best-evers would we expect?

## Doubling Interval


A simple heuristic approach would be to argue like this: at any given moment, there will have been a total of n students, of which 1 will be the best; if we then wait for the next n students, the best in that will presumably be equal to the previous best, since the two groups of students are otherwise equal; so we expect a best-yet for every doubling of total n; we simply see how many doublings there are.


If new units arrive at a rate of m per year, this is a geometric series and the years necessary looks like: S = 1⧸m × (2k + 1 − 1) or ∑ik 2i / m. This grows logarithmically, and `ln(6,400) = 8.76`.


This might seem surprisingly high: over a 64-year career, the teacher would average a best-ever student every 7 years? (The average here is misleading because it would be heavily front-loaded, of course, but still.)


Is this right? Well, we can easily Monte Carlo simulate this scenario to check:


`set.seed(123)

n_students <- 100
n_years <- 64

## Define a function to simulate one teaching career
get_num_records <- function(){
  ## Generate all the student scores
  student_scores <- rnorm(n_students * n_years)

  ## Initialize the best score and number of records
  best_score <- -Inf
  num_records <- 0

  ## Iterate through each student's score
  for (score in student_scores) {
    ## If current score is a new record, update the best score
    ## and increment the number of records
    if (score > best_score) {
      best_score <- score
      num_records <- num_records + 1
    }
  }

  return(num_records)
}

## Run the simulation multiple times (eg. 1,000×)
num_runs <- 100000
all_records <- replicate(num_runs, get_num_records())

## Display the average number of records
mean(all_records)
# [1] 9.34807`


The doubling argument’s log heuristic is about the right order of magnitude, but noticeably wrong: it is off by ~0.58. Something is missing.


## Harmonic Series


Another way to put it would be to observe that given n students thus far, what is the probability that the next student will be the best-yet?


Only 1 student can be the best, so the probability is 1⧸n. If we start from the first student, then the second student, and so on, we wind up summing a series like 1 + 1⁄2 + 1⁄3 + … + 1⧸n. What does that sum to?


If we check references, we learn that the sum of the harmonic series up to n is:


E = 1 + 1⁄2 + 1⁄3 + … + 1⧸n ≈ ln(n) + γ


So, we expect to witness around ln(n) + γ record-breaking events.


We see the natural log again as expected, but also a ‘+ γ’—what is this ‘γ’? γ is the Euler-Mascheroni constant (0.57721…) which accounts for the difference between the sum of the harmonic series and the integral of the reciprocal function.


This accounts for the gap between our log heuristic and the Monte Carlo simulation: if the teacher sees 6,400 students in their career (100 students per year for 64 years), we’d expect about ln(6,400) + γ ≈ 8.76 + 0.57721 ≈ 9.337, which matches the simulation within sampling error.


So, we are right after all: a teacher teaching a constant small flow of students could see a surprising number of best-yet students, and honestly be able to write ≫1 letters of recommendation stating “Best student I ever had”.



Error: JavaScript disabled.

Backlinks, similar links, and the bibliography require JS enabled to load.
        # Similar Links


        [Similar links by topic]




        [&hairsp;Send Anonymous Feedback&hairsp;]

[Quote Of The Day]

[Site Of The Day]

[Annotation Of The Day]

[adblock public service announcement]

      ​
