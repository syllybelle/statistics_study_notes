# Lecture Notes

## Definitions and notation

- `experiment`: any action or process that generates observations
- `sample space`: $S$ all posssible outcomes
- `cardinality`: $|S|$ the number of outcomes contained in a set ($S$ or $A$)
- `probability`: derive characteristics of a sample from known population characteristics
- `statistics`: derive characteristics of a population based on known characteristics of a sample
- `Naive probability` $P(event) = \frac{|A|}{|S|}$ - i.e. no weighting for likelihood of outcomes. In contrast with
  conditional probability
- `Permutation`: $P_{k,n}$   : &emsp; ordered sequence of _k_ objects taken from a set of _n_ distinct objects  
  $|S_{P}| = \frac{n!}{(n-k)!}$
- `Combinations`: $C_{k,n}$ : unordered subset of size k of n distinct objects. order is not important  
  $|S_{C}| = \frac{n!}{(n-k)!k!} = {n \choose k}$
- `binomial coeeficient`:  the number of ways that x objects can be chosen from a population of n objects.
- `Union`: $A \cup B$ = A or B
- `Intersection`: $A \cap B$ = A and B
- `Complement`: $A^{c}$ or $\overline{A}$: everything except A.
- `Disjoint sets`: $A \cap B = \phi$
- `Partitions`: disjoint subsets that cover all outcomes in A: $A \cup A^{c} = S$
- $k \binom {n}{k}$ : number of ways one object can be picked from subset of length k, from set of length n
- `conditional probability`: $P(A|B)$ : the probability of A given that B occured; if B, then `P(A)...` - in contrast to
  naive probability  
  $P(A|B) = \frac {P(A \cap B)}{P(B)}$ **NB: do not confuse symbols '|' ('given') and '$\cup$' ('or')))**
- `assumed equivalence`: `$A:=B$ assuming/given that/when A is equivalent to B
- `marginal probability`: Marginal probability is the probability of an event irrespective of the outcome of another
  variable.

<details>
  <summary> A summary, to clarify the shape of things, etc </summary>

just because I lost a lot of time being very confused about this
An event/outcome is often seen referred to both as a single object as part of a larger sample space, but also as a set
itself,
containing observations.

Consider:
50 of 100 people drive to work (A), 25/100 get coffee before work (B), 10/100 do both ($A \cap B$).

This is how the venn diagram number would look:
A only = (50-10)   
B only = (15-10)  
both = 10
(neither = 45)
The numbers refer to the observations. in this way, these events are seen as sets containing observations, each set
partitioning the sample space of possible outcomes.

but the venn diagram itself is a set containing all possible outcome combinations.
we have a new sample space of all possible outcomes (this maps to the segments in the venn diagram)
but when looking at probabilities, we can then look at all possible combinations of these events occuring, for example,
the probability of people driving to work (whether or not they get coffee)
the probability of people driving to work or getting coffee, but not both.
Now we have a new space of all possible combinations of outcomes (these are often coin flipping examples),
Now, with the 4 compartments of the venn diagram (A only, B only, both A and B, neither), we have 24 different
combinations of outcomes and this is where binomial coefficients and permuitations and combinations come in.
And this can fuck right off.

</details>

<br>

## Axioms & conventions

Axiom: a statement or proposition which is regarded as being established, accepted, or self-evidently true.

- $A$: set or event
- $0! = 1$
- Empty set: $\phi$
- For any event $A$, $0 \le P(A) \le 1 $
- $P(S) = 1$
- If $A_{1}, A_{2} ... A_{n}$ are a collection of mutually exclusive (disjoint) events, then the probability of the
  union of those events equals the sum of the individual probabilities.  
  if $P(A) = 0.20$ and $P(B) = 0.15$, then $P(A \cup B) = 0.35$  
  $P(\cup_{n}^{k=1} A_{k}) = \displaystyle\sum_{k=1}^n P(A_{k})$

Based off the above:

- $A \cup A^{c} = S$
- $A \cap A^{c} = \phi$
- $P(A^{c}) = 1-P(A)
- if $A \cap B = 0$, then $P(A \cap B) = 0$
- $P(A \cup B) = P(A) + P(B) - P(A \cup B)$

## Basic probability operations

`multiplication rule`:  used to find the probability of two events happening at the same time $P(A \cap B) = P(A) ??? P(B)
$. For a combination of k objects that have n options: $n_{1} ??? n_{2} ??? ... ??? n_{k} = n^{k}$

`factorial`: number of combinations for k objects that have n options where n options cannot be reused ('replaced'):
$ {n ??? (n-1) ??? ... ??? (n-k) = \frac{n!}{k!}}$  
`binomial coefficient` : 'n choose k' ${n \choose k} = \frac{n!}{(n-x)!x!}$ : for all combinations of n ($n!$),
divide out options exceeding the number of choices required ($n-k$)! and remove permutations (x!)  (options that have
the same choices in diffferent orders)  
`Bose-Einstein result`: pick $k$ objects from set of size $n$ with replacement, and order does not matter (objects in
set are not unique)
n identical objects can be divided into r groups where each group can have any number of objects, including 0

### Sampling table

|                  | order matters         | order does not matter |
|------------------|-----------------------|-----------------------|
| with replacement | $n^{k}$               | $n+k-1 \choose k$     |
| w/o replacement  | $\frac {n!} {(n-k!)}$ | $n \choose k$         |

<details>
  <summary> Example: ordered sampling, with replacement</summary>

> How many permutations of a 4-digit number can be made (e.g. dial lock), where each digit can be sampled from [0-9]
> with replacement, where order matters
> - simple multiplication: $10 x 10 x 10 x 10$

</details>

<br>

<details>
  <summary> Example: ordered sampling, without replacement</summary>

> how many 4-letter combinations are there from a 7-letter scrabble hand (assuming 7 unique letters)
> - simple factorial multiplication, $7 x 6 x 5 x 4 = \frac{7!}{(7-4)!}$

</details>

<br>

<details>
  <summary> Example: unordered sampling, without replacement</summary>

> How many permutations of a 7 letter string can be made using 3 letter As and 4 letter Bs
> - the unique ways can 3 indices (locations) in the sequence be chosen for the A to be in (all combination of 3 unique
    locations)
> - the unique ways can 4 indices in the sequence be chosen for the B to be in (all combination of 4 unique locations)
> - the locations are unique ("without replacement", but the order in which they are selected does not matter:
    indices [1, 3, 4] = indices [4, 3, 1] = BABAABB (assuming a 0 index)
> - choose 4 from 7 $P_{k,n}$

</details>

<br>

<details>

  <summary> Example: unordered sampling, with replacement</summary>

> How many "combinations" of a 4-digit number (e.g. button lock) can be made, where each digit can be sampled from [0-9]
> , order does not matter
> - order of selecting the four digits does not matter
> - sample 4 items from 10 options, replacing without removing the selected value from the set of 10. how many different
    samples can be taken?
>
> The ball and box metaphor
> - how many of each digit are in the sample (always sum to k/sample size). $i_{0} + i_{1} + i_{2} + ... + i_{9} = 4; i
    \in \mathbb{Z}_+$
> - How many answers are there to the above equation?
> - How many ways can four "balls" (the unordered digits) be re-arranged between 10 "containers"?  
    > `| ???????????? | | | | | | | | | |`  
    > `| ????????? | ??? | | | | | | | | |`
> - in the top example, all four digits are in the first box, so the lock combination is "0 0 0 0", in the next, any
    permutation of "1 0 0 0"
> - how many times can the positions of the internal "container walls `|`" and the "balls `???`" be rearranged?
> - simple unordered sampling without replacement: selecting four unique indices from a possible 13 (there cannot be any
    balls outside the box, the external walls are not counted)

</details>

## Conditional probability

Probability that A occurs given that B occurs: $P(A|B)=\frac{P(A \cap B)}{P(B)}$

- the probability of A given B, is the probability of A & B occuring, over the probability of B occurring (B := S $$).

!> **NB: do not confuse symbols '|' ('given') and '$\cup$' ('or')))**

|                  | B occurs       | B does not occur   |         |
|------------------|----------------|--------------------|---------|
| A occurs         | $A \cap B$     | $A \cap B^{c}$     | $A$     |
| A does not occur | $A^{c} \cap B$ | $A^{c} \cap B^{c}$ | $A^{c}$ |
|                  | $B$            | $B^{c}$            | $S$     |

### Law of total probability

- The overall probability of A, if the probability of A changes depending on whether B has occurred
    - now using total sample space, so divide by $(P(S)) = 1$
    - Multiplication rule (see above): the probability of two events happening at the same time  
      $$ P(S) = P(A \cap B^{c}) + P(A \cap B) + P(A^{c} \cap B^{c}) + P(A^{c} \cap B) $$
      $$ 1 = P(A)???P(B^{c})  + P(A)???P(B) + P(A^{c})???P(B^{c}) + P(A^{c})???P(B) $$

- the `marginal probability` refers to the probability of an event occuring independent of other outcomes, and is the
  sum
  of the conditional probabilities. (I refer to the marginal probability as the global probability sometimes)

<br>

<details>

  <summary> Example</summary>


> What is the probability that Anne will walk to work, if P(walk) is .95 when not raining, and P(walk) is .3 when
> raining, and P(raining) is .4
> - $P(A|B)= P(A)???P(B^{c}) + P(A)???P(B)$  
    > $ = 0.95 ??? 0.60 + 0.3 ??? 0.4$   
    > = <abbr title="lol">0.69</abbr>


</details>

### Bayes' rule

Given two events A and B, the conditional probability of A given that B is true and ($P(B) \ne 0 $):
$$P(A|B) = \frac {P(B|A)???P(A)}{P(B)} = \frac {P(A \cap B)}{P(B)}$$
$$P(A|B)???P(B) = P(B|A)???P(A) = P(A \cap B)$$

<details>

  <summary> Defining Bayesian statistics: </summary>

?> ** Wikipedia definition **  
Bayesian statistics is a theory in the field of statistics based on the Bayesian interpretation of probability where
probability expresses a degree of belief in an event. The degree of belief may be based on prior knowledge about the
event, such as the results of previous experiments, or on personal beliefs about the event. This differs from a number
of other interpretations of probability, such as the frequentist interpretation that views probability as the limit of
the relative frequency of an event after many trials.

</details>

In the context of conditional probability, Bayes' Rule allows for conversion between $P(A|B)$ and $P(B|A)$

Often $P(B)$ is unknown, and it is more useful to convert it to the marginal $P(B)$ using the law of total probability:
$P(B) = P(B|A) ??? P(A) + P(B|A^{c}) ??? P(A^{c})$, such that:

$$P(A|B) = \frac {P(B|A)???P(A)}{P(B)} = \frac {P(A \cap B)}{P(B|A) ??? P(A) + P(B|A^{c}) ??? P(A^{c}}$$

> In words: given A, the probability of B is:
> - the overall probability that both A and B occur - the probability that A occurs given B multiplied by the overall
    probability of A occurring)
> - divided by the sample space - the overall probability that B has occured - the probability that b occured in the
    context of A, weighted by the probability that A occurred, plus the probability that b occured in the context of A
    not occured, weighted by the probability that A did not occur

<details>

  <summary> Example</summary>

> What is the probability that A occured (sam went along), given that B occured (frodo arrived)?  
> Known:
> - $P(B|A) = .9$: the relative probability of frodo arriving, given that sam came
> - $P(B|A^(C)) = .1$ the relative probability of frodo arriving, given that sam did not come
> - $P(A) = 0.8$ the overall probability that sam comes
> - $P(A^(C)) = 0.2$ the overall probability that sam does not come (summing of partitions)
    > solve P(A|B)
>
> P(sam coming given that frodo arrived) is the overall probability that both frodo arrived and sam came, dividing
> out the probability that frodo did not arrive (removing those outcomes from the sample space).
> $$P(A|B) = \frac{P(B \cap A)}{P(B)}$$  
> However, we do not have either of those terms.  
> To calculate the numerator $\frac{P(B \cap A)} (multiplication rule)$:
> - The global probability that both sam and frodo arrived is the probability of frodo arriving if sam comes, modified
    by the global likelihood of sam coming
>
> > $P(B \cap A) = P(B|A) ??? P(A) = 0.9 ??? 0.8$ such that $P(A|B)= P(0.9 ??? 0.8) = 0.72$  
> To calculate the denominator $P(B)$ (law of total probability):
> - The global probability of frodo arriving is the probability of
    >

- frodo arriving when sam does not come, weighted by the probability of sam coming,

> - plus the probability of frodo arriving weighted by the probability of sam not coming
>
> > $(B) = P(B|A) ??? P(A) + P(B|A^{c}) ??? P(A^{c}) = 0.9 ??? 0.8 + 0.1 ??? 0.2 = 0.74$
>
> $$P(A|B)= \frac {0.72}{0.74} = 0.97$$  
> There is a 0.97 chance that sam has come with
>

</details>

### Inclusion/Exclusion

Finding the probability of the union of multiple events (calculating the total sample in a venn diagram), which is
complicated by overcounting
$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

The number of compartments which is the union of k out of n outcomes is the binomial coefficient of the number of event outcomes 
(in a three circle diagram, the number of compartment containing experiments for a single outcome ("singles") is $\binom{3}{1} = 
3$, containing two outcomes ("doubles") is $\binom{3}{2} = 3$, containing 3 outcomes "triples" is $\binom{3}{3} = 1$)

To account for overcounting, this generification can be applied:  
$$P(Union of many Events) = P(Singles) - P(Doubles) + P(Triples) - P(Quadruples) ...$$

This is useful in unordered matching problems without replacement (likelihood of matching with your pair)  

<details>

  <summary> De Montmort's Pair Matching Problem </summary>

> there are two sets: e.g. people and hats. Each person has a matching hat (forming a pair), but both sets are shuffled.
> Find P(A): probability that at least one pair is matched when they try to join.
> - basic approach: say we have three people-hat pairs

| Person a | Person b | Person c | 1   | 2   | 3   | n matches |
|----------|----------|----------|-----|-----|-----|-----------|
| Hat A    | Hat B    | Hat C    | 1   | 1   | 1   | 3         |
| A        | C        | B        | 1   |     |     | 1         |
| B        | A        | C        |     |     | 1   | 1         |
| B        | C        | A        |     |     |     | 0         |
| C        | A        | B        |     |     |     | 0         |
| C        | B        | A        |     | 1   |     | 1         |

> - 4/6 outcomes have at least 1 match, 
> - 1/6 has has 3 matches,
> - 0/6 have two matches
> - 3/6 have 1 match
> - 2/6 have 0 matches

> Definitions:
> - n = number of pairs (so there are 2n objects)
> - i = the identity/index of an item from one list (in this example, a hat)
> - j = the identity/index of one item from another list (in this example, a person)
> - E = a hypothetical (past) event used to calculate situational probabilities: a single hypothetical selecting a hat is an 
    event $E_{ij}$, that can be either be a match (1 - they have selected their own hat) or not match (0)
> - c = a combination of E events, such that  every individual has selected a hat (c = set$[E_{0} E_{1} ... E_{n}]$))
> - S = the total space of all possible c s (every possible combination between hats & people)
> 
> $P(A) = frac{|S_{c where n(E=1) > 0}|}{S} $
> Building up the probability space:  
> - a hypothetical person (i) selecting a hat (j) from a pool of n hats has: $P(E_{ij} = 1) = \frac{1}{n}$
> - the probability of every hypothetical individual selecting the right hat in a lineup (c): $P(c  1)\frac{1}{n!}$ 
> - the probability of at least one hypothetical matchup in a lineup (c):  
>   - each match event has probability $frac{1}{n-i}$ of being a match
>   - if this probability is represented in a circle on a venn diagram with n circles, the probability of at least one matchup 
      > could be considered to be the union of all the circles
>   - if there are three people with three hats:
>     - the first person has a 1/3 chance
>     - the second person has a 1/2 chance
>     - the third person has a 1/
> 
> - to calculate the number of different combinations that can be made between people and hats: $|S| = n!$:  
>   - given that the order in which people choose hats doesn't matter:  
>   - can be thought of permutations of hat orders: matching an index with a hat  
> 
> - $\frac {n!} {(n-k)!} ; n = k \therefore (n-k)! = 1$  
> The proability P(A_{})
> if we consider each matchup between a hat and a particualar person for all n! combinations of hat-person pairs an event, 
> then the probability of that hat-person matchup is the number of combinations in which that matchup occurs, over all 
> combinations.
> 
> the probability of a person matching with the right hat in a single matchup event is $n$, the next person has an $(n-1)$
> chance, etc. 
> this is a set of events, and we are considering permutations.
> (In case this helps with context: A simple probability that the hats are in the right order, is n!)
> The number of possible matchups is an ordered permutation problem without replacement
> The chance of at least one pair matching up is sum of the combinations in which at least one matchup occurs divided by all 
> possible combinations
> 
> P(A) = union of a meetup event
> $S_{n}$: number of successful matches given n party goers


</details>  

<br>
<br>




<details>

  <summary> Example</summary>  

jhk 

</details>  


# Katex ref

`01`  $\sum_{n=1}^{10} n^2$  
`02`  
`03`  $x = y $  
`04`  $x < y $  
`05`  $x > y $  
`06`  $x \le y $  
`07`  $x \ge y $  
`08`  $x^{n}$  
`09`  $x_{n}$  
`10`  $\overline{x}$  
`11`  $\hat{x}$  
`12`  $\tilde{x}$  
`13`  $\frac{a}{b}$  
`14`  $\frac{\partial f}{\partial x}$  
`15`  $\displaystyle \frac{\partial f}{\partial x}$  
`16`  $\binom{n}{k}$  
`17`  $x_{1} + x_{2} + \cdots + x_{n}$  
`18`  $x_{1}, x_{2}, \dots, x_{n}$  
`19`  $x=???x1,x2,???,xn??? \mathbf{x} = \langle x_{1}, x_{2}, \dots, x_{n}\rangle$  
`20`  $x \in A$  
`21`  $|A|$  
`22`  $x \in A$  
`23`  $x \subset B$  
`24`  $x \subseteq B$  
`25`  $A \cup B$  
`26`  $A \cap B$  
`27`  $X \sim {\sf Binom}(n, \pi)$ (sf for ???slide font???)  
`28`  $\mathrm{P}(X \le x) = {\tt pbinom}(x, n, \pi)$ (tt for ???typewriter type???)  
`29`  $P(A \mid B)$  
`30`  $\mathrm{P}(A \mid B)$ (mathrm for ???math roman font???  
`31`  $\{1, 2, 3\}$  
`32`  $\sin(x)$
`33`  $\log(x)$  
`34`  ???ba $\int_{a}^{b}$  
`35`  $\left(\int_{a}^{b} f(x) \; dx\right)$  
`36`  $\left[\int_{-\infty}^{\infty} f(x) \; dx\right]$  
`37`  $\left. F(x) \right|_{a}^{b}$  
`38`  $\sum_{x = a}^{b} f(x)$  
`39`  $\prod_{x = a}^{b} f(x)$  
`40`  $\lim_{x \to \infty} f(x)$  
`41`  $\displaystyle \lim_{x \to \infty} f(x)$  
`42`  $ \ne $  
`43` # Greek Letters  
`44`  ??A: $\alpha A$  
??N $\nu N$  
`45`  ??B: $\beta B$  
???? $\xi\Xi$  
`46`  ????: $\gamma \Gamma$  
oO $o O$ (omicron)  
`47`  ????: $\delta \Delta$  
???? $\pi \Pi$  
`48`  ????E: $\epsilon \varepsilon E$  
????P $\rho\varrho P$  
`49`  ??Z: $\zeta Z \sigma \,\!$  
?? $\sigma \Sigma$  
`50`  ??H: $\eta H$  
??T $\tau T$  
`51`  ??????: $\theta \vartheta \Theta$  
???? $\upsilon \Upsilon$  
`52`  ??I: $\iota I$  
?????? $\phi \varphi \Phi$  
`53`  ??K: $\kappa K$  
??X $\chi X$  
????: $\lambda \Lambda$  
???? $\psi \Psi$  
??M: $\mu M$  
???? $\omega \Omega$  

