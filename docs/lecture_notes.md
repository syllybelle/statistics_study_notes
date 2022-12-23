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
  $P(\cup_{n}^{k} A_{k}) = \displaystyle\sum_{k}^n P(A_{k})$

Based off the above:

- $A \cup A^{c} = S$
- $A \cap A^{c} = \phi$
- $P(A^{c}) = 1-P(A)
- if $A \cap B = 0$, then $P(A \cap B) = 0$
- $P(A \cup B) = P(A) + P(B) - P(A \cup B)$

## Basic probability operations

`multiplication rule`:  used to find the probability of two events happening at the same time $P(A \cap B) = P(A) ⋅ P(B)
$. For a combination of k objects that have n options: $n_{1} ⋅ n_{2} ⋅ ... ⋅ n_{k} = n^{k}$

`factorial`: number of combinations for k objects that have n options where n options cannot be reused ('replaced'):
$ {n ⋅ (n-1) ⋅ ... ⋅ (n-k) = \frac{n!}{k!}}$  
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
> - the generic problem: how many unique sets can  be created by selecting k identifiable objects from superset n
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
    > `| ⊛⊛⊛⊛ | | | | | | | | | |`  
    > `| ⊛⊛⊛ | ⊛ | | | | | | | | |`
> - in the top example, all four digits are in the first box, so the lock combination is "0 0 0 0", in the next, any
    permutation of "1 0 0 0"
> - how many times can the positions of the internal "container walls `|`" and the "balls `⊛`" be rearranged?
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
      $$ 1 = P(A)⋅P(B^{c})  + P(A)⋅P(B) + P(A^{c})⋅P(B^{c}) + P(A^{c})⋅P(B) $$

- the `marginal probability` refers to the probability of an event occuring independent of other outcomes, and is the
  sum
  of the conditional probabilities. (I refer to the marginal probability as the global probability sometimes)

<br>

<details>

  <summary> Example</summary>


> What is the probability that Anne will walk to work, if P(walk) is .95 when not raining, and P(walk) is .3 when
> raining, and P(raining) is .4
> - $P(A|B)= P(A)⋅P(B^{c}) + P(A)⋅P(B)$  
    > $ = 0.95 ⋅ 0.60 + 0.3 ⋅ 0.4$   
    > = <abbr title="lol">0.69</abbr>


</details>

### Bayes' rule

Given two events A and B, the conditional probability of A given that B is true and ($P(B) \ne 0 $):
$$P(A|B) = \frac {P(B|A)⋅P(A)}{P(B)} = \frac {P(A \cap B)}{P(B)}$$
$$P(A|B)⋅P(B) = P(B|A)⋅P(A) = P(A \cap B)$$

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
$P(B) = P(B|A) ⋅ P(A) + P(B|A^{c}) ⋅ P(A^{c})$, such that:

$$P(A|B) = \frac {P(B|A)⋅P(A)}{P(B)} = \frac {P(A \cap B)}{P(B|A) ⋅ P(A) + P(B|A^{c}) ⋅ P(A^{c}}$$

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
> > $P(B \cap A) = P(B|A) ⋅ P(A) = 0.9 ⋅ 0.8$ such that $P(A|B)= P(0.9 ⋅ 0.8) = 0.72$  
> To calculate the denominator $P(B)$ (law of total probability):
> - The global probability of frodo arriving is the probability of
    >

- frodo arriving when sam does not come, weighted by the probability of sam coming,

> - plus the probability of frodo arriving weighted by the probability of sam not coming
>
> > $(B) = P(B|A) ⋅ P(A) + P(B|A^{c}) ⋅ P(A^{c}) = 0.9 ⋅ 0.8 + 0.1 ⋅ 0.2 = 0.74$
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
$$P(Union\enspace of\enspace many\enspace Events) = P(Singles) - P(Doubles) + P(Triples) - P(Quadruples) ...$$

Representing an event as $A_{i}$:
$$P(A_{1} \cup A_{2} \cup ... \cup A_{n}) = P(A_{0}) + P(A_{1}) + P(A_{n}) + ... - P(A_{0} \cap A_{1}) - $$
$$P(A_{0} \cap A_{3}) - ... - P(A_{n-1} \cap A_{n}) -  ... +/- P(intersection\enspace of\enspace all\enspace circles) $$

(I like zero indexing things, sorry - so there are a lot of (n-1)s lying around)
$$P(\cup_{i=0}^{n-1} A_{i}) = \sum_{i=0}^{n-1} P(A_{i}) - \sum_{i=0; i < j}^{n-1} P(A_{i} \cap A_{j})  + \sum_{i=0; i < j < k}^
{n} P(A_{i} \cap A_{j}  \cap A_{k}) + (-1)^{n+1} ⋅ P(A_{0} \cap ... \cap A_{n-1})$$

<details>

  <summary> where does the that last term come from?</summary>  

> $(-1)^{n+1}$ TLDR: it's to make the signs correct
> - the sign of the last term will depend on whether the number of intersecting events is even (will be subtracted) or 
odd  (will be added). the number of intersecting events in the last term is n (the intersection of all events).
> - A positive sign can be derived by multiplying a term by (-1) by an even multiple, and a negative sign can be derived by 
multiplying (-1) by an odd multiple. To derive a negative sign from  an even (n) from the last term, we must offset n by 
one: $(-1)^{n+1}$
>   - in this case, because n is a count of the number of terms, not an index, it is not zero indexed, so you just use plain 
      > old n. but then offset by one. because of the way that it is.
> - This is useful in unordered matching problems without replacement (likelihood of matching with your pair)  
> 
> why is there no sigma? 
> - there is only 1 section that represents the union of all events (the middle of the venn diagram), so there is only 1 
    > probability term to add/subtract.

</details>


<details>

  <summary> Application: De Montmort's [Pair] Matching Problem </summary>

> there are two sets: e.g. people and hats. Each person has a matching hat (forming a pair), but both sets are shuffled.
> Find P(A): probability that at least one pair is matched when they try to join.
> - brute force approach: say we have three people-hat pairs
>   - there are three people [Persona a, Person B and Person C]. person A owns Hat A, Person B owns Hat B and Person C owns 
      hat C. What is the probability that, after everyone has chosen a hat from a disordered pile, at least 1 person selects 
      their own hat.
>   - each row ($c_{n}$) represents a combination of hats people choose (for example the second row: person a chose hat a, 
      person b chose hat C and peson c chose hat b)
>   - the rows together represent all possible combinations of hat-people (sample space $S$)
>   - if we call a person choosing a hat (represented by a cell in the table) an event ($E$), each E can be assigned a 
      > value, depending on whether there was a match or not (match = 1, not a match = 0) or not a match (0).   
     $c_{1} = [E_{0}, E_{1}, E_{2}] = [1, 0 , 0]$ 
>   - the chance that a person receives their hat $P(E=1) = 2/6 = 1/3$ 
>   - the last column counts the number of matches that occured in the combination of hat-peeople pairs
>   - From the table below, it can be seen that at least one positive match (n matches >= 1) occured in $[c_{0}, c_{1}, c_{2}, c_
      > {5}]$ - i.e. 4 out of 6 combinations, so P(A) = 2/3
>   - note that rearranging the order of the people will not change the number of possible combinations

|         | Person a | Person b | Person c |     | a match     | b match     | c match     | n matches                |
|---------|----------|----------|----------|-----|-------------|-------------|-------------|--------------------------|
| $c_{0}$ | Hat A    | Hat B    | Hat C    | ->  | $E_{0} = 1$ | $E_{1} = 1$ | $E_{2} = 1$ | $\sum_{i=0}^{2} E_{i}=3$ |
| $c_{1}$ | A        | C        | B        | ->  | $E_{0} = 1$ | $E_{1} = 0$ | $E_{2} = 0$ | $\sum_{i=0}^{2} E_{i}$   |
| $c_{2}$ | B        | A        | C        | ->  | $E_{0} = 0$ | $E_{1} = 0$ | $E_{2} = 1$ | $\sum_{i=0}^{2} E_{i}$   |
| $c_{3}$ | B        | C        | A        | ->  | $E_{0} = 0$ | $E_{1} = 0$ | $E_{2} = 0$ | $\sum_{i=0}^{2} E_{i}=0$ |
| $c_{4}$ | C        | A        | B        | ->  | $E_{0} = 0$ | $E_{1} = 0$ | $E_{2} = 0$ | $\sum_{i=0}^{2} E_{i}=0$ |
| $c_{5}$ | C        | B        | A        | ->  | $E_{0} = 0$ | $E_{1} = 1$ | $E_{2} = 0$ | $\sum_{i=0}^{2} E_{i}$   |
 
> - Solving P(A) for n pair
>   - within a combination (c), the base probability of each person receiving their own hat in a whole lineup is equal $(P(E_{0}) = P(E_
        > {1}))$.
>     - the probability of the second person, given the result off the first person, will be different ($P(E_{1} | E_
        > {0})$, but at naively, before anyone starts choosing hats, the first and the second person have the same probability.
>     - the number of combinations in which a hat matches with the correct person(E=1): $(n-1)!$.
>       - this is because there are (n-1) hats which have (n-1)! person-hat combinations.
>       - using the example above, in what proportion of rows will person a match with their hat: hat A becomes fixed, so the 
          > number of combinations is determined by the number of ways the remaining hats can be arranged
>   - $|S| = n!$: there are n! possible combinations of n people choosing n hats ($n \choose n$$= n!$)
>   - the probability of everyone choosing their own hat: $ P(\sum_{i=0}^{n} E_{i}=n) = \frac{1}{n!}$ 
>   - the probability of a hat being correctly chosen (this is the same as a person choosing a hat) $P(E)$:
>     - of the n! combinations, in how many a person receive their hat
>     - given that we do not know when the process a hat will be chosen
>   - the probability of at least one matchup occuring ($E_{0} = 1$ or $E_{1} = 1$ etc. ) can be defined as: $ P(\sum_{i=0}^{n} E_
      > {i} >= 1)$ or as the union of the probabilities.
>   - this is essentiallly the union of the probabilities of all events being positive (each event is a circle in a venn diagram)
>     - any of the events can be positive, so it is the union of all circles
>     - the intersection of all circles would be the probability that all events are a match - i.e. 1/n!
> 
>   - We can therefore apply the inclusion formula above.
>   - Because no person is more or less likely than another to get their own hat i.e. "symmetry", terms can be simpllifid:
>     - $\sum_{i=0}^{n-1} P(A_{i})$:
>       - $P(E_{0}=1) + P(E_{1}=1) + ... + P(E_{n-1}=1) = n  ⋅ P(E_{0}=1)$ 
>       - $P(E_{0}=1)$ : number of events in which a person gets their hat out of all possible person-hat combinations
>       - As shown above: $\frac{(n-1)!}{n!}$
> 
>       - $\sum_{i=0}^{n-1} P(A_{i}) = n  ⋅ \frac{(n-1)!}{n!}$
>     - $\sum_{i < j} P(A_{i} \cap A_{j})$
>       - the number of combinations of two events = $n \choose 2$
>       - the probability of two hats being chosen by their owners follows the same logic: if we fix 2 events, there are $(n-2)!$
          combinations of the remaining events, so  $P(A_{i} \cap A_{j}) = \frac{(n-2)!}{n!}$
>       - $ \binom{n}{2}  ⋅ \frac{(n-2)!}{n!}$
>     - the $k^{th}$ term: $ \binom{n}{k}  ⋅ \frac{(n-k)!)!}{n!}$ 
>       - $\frac{n!}{(n-k)!k!} ⋅ \frac{(n-k)!)!}{n!} = \frac{n!(n-k))!}{n!(n-k)!k!} = \frac{(1}{k!}$
>       - when k = 1: $\frac{1}{1!} = 1$
>       - when k = n: $\frac{1}{n!}$
>     - $P(\cup_{i=0}^{n-1} A_{i}) = \sum_{k=1}^{n} \frac{1}{k!} ⋅ (-1)^{k+1}$
>     - $P(\cup_{i=0}^{n-1} A_{i}) = 1 - \frac{1}{2!} + ...$
>   - This can be calculated using a [Taylor's Series](https://www.wikiwand.com/en/Taylor_series) 
>     - tldr: an infinit sum of  terms expressed in terms of a function's derivitives -> there are examples [here](https://people.math.sc.edu/girardi/m142/handouts/10sTaylorPolySeries.pdf)
>     - the adaptable Taylor series in question: $ e^{x} \approx 1 + x + \frac{x^{2}}{2!} + ... \frac{x^{k-1}}{k!}+ ... $
>     - $e^{-1} = 1/e \approx (1 - 1) + \frac{1}{2!} - \frac{1}{2!}) + ... + (-1)^{k}⋅ \frac{1}((k+1)!) 
> $P(A) \approx 1 - \frac{1}{e}$
> <hr/> 
>
</details>





<details>

  <summary> Example</summary>  

jhk 

</details>  


# Katex ref

`01  $\sum_{n=1}^{10} n^2$` $\sum_{n=1}^{10} n^2$  
`02  ` 
`03  $x = y $` $x = y $  
`04  $x < y $` $x < y $  
`05  $x > y $` $x > y $  
`06  $x \le y $` $x \le y $  
`07  $x \ge y $` $x \ge y $  
`08  $x^{n}$` $x^{n}$  
`09  $x_{n}$` $x_{n}$  
`10  $\overline{x}$` $\overline{x}$  
`11  $\hat{x}$` $\hat{x}$  
`12  $\tilde{x}$` $\tilde{x}$  
`13  $\frac{a}{b}$` $\frac{a}{b}$  
`14  $\frac{\partial f}{\partial x}$` $\frac{\partial f}{\partial x}$  
`15  $\displaystyle \frac{\partial f}{\partial x}$` $\displaystyle \frac{\partial f}{\partial x}$  
`16  $\binom{n}{k}$` $\binom{n}{k}$  
`17  $x_{1} + x_{2} + \cdots + x_{n}$` $x_{1} + x_{2} + \cdots + x_{n}$  
`18  $x_{1}, x_{2}, \dots, x_{n}$` $x_{1}, x_{2}, \dots, x_{n}$  
`19  $x=⟨x1,x2,…,xn⟩ \mathbf{x} = \langle x_{1}, x_{2}, \dots, x_{n}\rangle$` $x=⟨x1,x2,…,xn⟩ \mathbf{x} = \langle x_{1}, x_{2}, \dots, x_{n}\rangle$
`20  $x \in A$` $x \in A$  
`21  $|A|$` $|A|$  
`22  $x \in A$` $x \in A$  
`23  $x \subset B$` $x \subset B$  
`24  $x \subseteq B$` $x \subseteq B$  
`25  $A \cup B$` $A \cup B$  
`26  $A \cap B$` $A \cap B$  
`27  $X \sim {\sf Binom}(n, \pi)$ (sf for “slide font”)` $X \sim {\sf Binom}(n, \pi)$ (sf for “slide font”)  
`28  $\mathrm{P}(X \le x) = {\tt pbinom}(x, n, \pi)$ (tt for “typewriter type”)` $\mathrm{P}(X \le x) = {\tt pbinom}(x, n, \pi)$ (tt for “typewriter type”)  
`29  $P(A \mid B)$` $P(A \mid B)$  
`30  $\mathrm{P}(A \mid B)$ (mathrm for “math roman font”` $\mathrm{P}(A \mid B)$ (mathrm for “math roman font”  
`31  $\{1, 2, 3\}$` $\{1, 2, 3\}$  
`32  $\sin(x)$` $\sin(x)$
`33  $\log(x)$` $\log(x)$  
`34  ∫ba $\int_{a}^{b}$` ∫ba $\int_{a}^{b}$  
`35  $\left(\int_{a}^{b} f(x) \; dx\right)$` $\left(\int_{a}^{b} f(x) \; dx\right)$  
`36  $\left[\int_{-\infty}^{\infty} f(x) \; dx\right]$` $\left[\int_{-\infty}^{\infty} f(x) \; dx\right]$  
`37  $\left. F(x) \right|_{a}^{b}$` $\left. F(x) \right|_{a}^{b}$  
`38  $\sum_{x = a}^{b} f(x)$` $\sum_{x = a}^{b} f(x)$  
`39  $\prod_{x = a}^{b} f(x)$` $\prod_{x = a}^{b} f(x)$  
`40  $\lim_{x \to \infty} f(x)$` $\lim_{x \to \infty} f(x)$  
`41  $\displaystyle \lim_{x \to \infty} f(x)$` $\displaystyle \lim_{x \to \infty} f(x)$  
`42 `
`43 # Greek Letters`  Greek Letters  
`44  αA: $\alpha A$ νN $\nu N$` αA: $\alpha A$ νN $\nu N$  
`45  βB: $\beta B$ ξΞ $\xi\Xi$` βB: $\beta B$ ξΞ $\xi\Xi$  
`46  γΓ: $\gamma \Gamma$ oO $o O$ (omicron)` γΓ: $\gamma \Gamma$ oO $o O$ (omicron)  
`47  δΔ: $\delta \Delta$ πΠ $\pi \Pi$` δΔ: $\delta \Delta$ πΠ $\pi \Pi$  
`48  ϵεE: $\epsilon \varepsilon E$ ρϱP $\rho\varrho P$` ϵεE: $\epsilon \varepsilon E$ ρϱP $\rho\varrho P$  
`49  ζZ: $\zeta Z \sigma \,\!$ Σ $\sigma \Sigma$` ζZ: $\zeta Z \sigma \,\!$ Σ $\sigma \Sigma$  
`50  ηH: $\eta H$ τT $\tau T$` ηH: $\eta H$ τT $\tau T$  
`51  θϑΘ: $\theta \vartheta \Theta$ υΥ $\upsilon \Upsilon$` θϑΘ: $\theta \vartheta \Theta$ υΥ $\upsilon \Upsilon$  
`52  ιI: $\iota I$ ϕφΦ $\phi \varphi \Phi$` ιI: $\iota I$ ϕφΦ $\phi \varphi \Phi$  
`53  κK: $\kappa K$ χX $\chi X$ λΛ: $\lambda \Lambda$ ψΨ $\psi \Psi$ μM: $\mu M$ ωΩ $\omega \Omega$` κK: $\kappa K$ χX $\chi X$ λΛ: $\lambda \Lambda$ ψΨ $\psi \Psi$ μM: $\mu M$ ωΩ $\omega \Omega$
