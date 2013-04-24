<!-- 
.. title: What Makes Code Hard to Understand?
.. slug: what-makes-code-hard-to-understand
.. date: 2013/04/18 11:10:01
.. tags: 
.. link: 
.. description: 
-->

What factors impact the comprehensibility of code? Psychology of programming
research suggests that expectation-congruent programs should take less time to
understand and be less prone to errors.  In this blog post, I'll describe an
experiment I did with my advisors [Andrew Lumsdaine](http://osl.iu.edu/~lums/)
(Computer Science) and [Rob
Goldstone](http://cognitrn.psych.indiana.edu/rgoldsto/) (Cognitive Science) at
Indiana University.

We asked 162 programmers to predict the output of [10 small Python
programs](../pages/eyecode-programs.html).  Each program had 2 or 3 different
versions, and we used subtle differences between program versions to
demonstrate that seemingly insignificant notational changes can have big
effects on correctness and response times. Our results show that experience
increases performance in most cases, but may hurt performance significantly
when underlying assumptions about related code statements are violated.

<!-- TEASER_END -->

## The Programmers

We had 162 programmers (129 males, 30 females, 3 unreported) participate from
Amazon's Mechanical Turk (130 people), the local Bloomington, IN area (29
people), and via e-mail solicitations (3 people). All participants needed to
have some programming experiments, and the Mechanical Turkers were required to
pass a simple Python quiz before taking the experiment.

Here's a breakdown of the participant demographics:
![Demographics](../assets/img/plot-demographics.png)

We paid the local participants $10 each because they also had to come in to the
lab and do the experiment in from of an eye-tracker (see my [previous
post](modeling-how-programmers-read-code.html) for a video). The folks from
Mechanical Turk got $0.75, which is a lot more than the penny I see most people
offering for surveys!

## The Experiment

The experiment consisted of a pre-test survey, ten trials (one program each),
and a post-test survey. The pre-test survey gathered information about the
participant's age, gender, education, and experience. Participants were then
asked to predict the printed output of ten short Python programs, one version
randomly chosen from each of ten program types.

Here's a shot of the main screen that participants used to drill down into each
trial:

![Main Screen](../assets/img/eyecode_home.png)

An individual trial consisted of the program's code (unhighlighted) and a text
box where the participant could write what they thought the program would
output.

![Main Screen](../assets/img/eyecode_trial.png)

The presentation order and names of the programs were randomized, and all
answers were final (i.e., no going back).  Although every program produced
error-free output, participants were not informed of this fact beforehand. The
post-test survey gauged a participant's confidence in their answers and the
perceived difficulty of the task.

## Results

We collected a total of 1,602 trials from the 162 participants starting
November 20, 2012 and ending January 19, 2013. Trials were graded
semi-automatically using a custom grading script ([available
here]([https://github.com/synesthesiam/eyecode-tools)). Grades were assigned like this:

* Perfect (10 points) - response exactly matched the program's output (about
  63% of trials)
* Correct (7-9 points) - response had the right numbers or letters, but
  incorrect formatting -- e.g., wrong whitespace, commas, brackets.
* Common error (2-4 points) - response was incorrect, but given by at least 3
  other participants

All other responses were graded manually. Any trial that was restarted was
discarded (i.e., the participant reloaded the web page or fiddled with the URL
to try and change their answer).

We had a total of 25 Python programs in 10 different categories. These programs
were designed to be understandable by a wide audience, and therefore did not
touch on Python features outside of a first or second introductory programming
course. The programs ranged in size from 3 to 24 lines of code (LOC).
Additional metrics, like [cyclomatic
complexity](http://en.wikipedia.org/wiki/Cyclomatic_complexity) and [Halstead
volume](http://en.wikipedia.org/wiki/Halstead_complexity_measures), were
computed with [PyMetrics](http://sourceforge.net/projects/pymetrics/).

### between (2 versions)

### counting (2 versions)

### funcall (3 versions)

### initvar (3 versions)

### order (2 versions)

### overload (3 versions)

### partition (3 versions)

### rectangle (3 versions)

### scope (2 versions)

### whitespace (2 versions)
