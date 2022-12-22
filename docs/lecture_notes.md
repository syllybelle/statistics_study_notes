> _while i'm debugging the sidebar (which works locally but not after deployment) here are the links:_  
> * [Home](/)  
> * [Lecture Notes](lecture_notes.md)  
> * [R notes](r_notes.md)  

# Lecture Notes

## Definitions and notation
- `experiment`: any action or process that generates observations
- `sample space`: $S$ all posssible outcomes
- `cardinality`: $|S|$  the number of outcomes contained in a set ($S$ or $A$)
- `probability`: derive characteristics of a sample from known population characteristics
- `statistics`: derive characteristics of a population based on known characteristics of a sample
- `Naive probability` $P(event) = \frac{|A|}{|S|}$ - i.e. no weighting for likelihood of outcomes. In contrast with conditional probability
- `Permutation`: $P_{k,n}$   : &emsp; ordered sequence of _k_ objects taken from a set of _n_ distinct objects  
$|S_{P}| = \frac{n!}{(n-k)!}$  
- `Combinations`: $C_{k,n}$ : unordered subset of size k of n distinct objects. order is not important  
$|S_{C}| =  \frac{n!}{(n-k)!k!} = {n \choose k}$ 
- `binomial coeeficient`:  the number of ways that x objects can be chosen from a population of n objects.
- `Union`: $A \cup B$  = A or B
- `Intersection`: $A \cap B$  = A and B
- `Complement`: $A^{c}$ or $\overline{A}$: everything except A. 
- `Disjoint sets`: $A \cap B = \phi$ 
- `Partitions`: disjoint subsets that cover all outcomes in A: $A \cup A^{c} = S$
- $k \binom {n}{k}$ : number of ways one object can be picked from subset of length k, from set of length n
- `conditional probability`: $P(A|B)$ : the probability of A given that B occured; if B, then `P(A)...` - in contrast to naive probability  
$P(A|B) = \frac {P(A \cap B)}{P(B)}$ **NB: do not confuse symbols '|' ('given') and '$\cup$' ('or')))**
- `assumed equivalence`: `$A:=B$ assuming/given that/when A is equivalent to B

## Axioms & conventions  
Axiom: a statement or proposition which is regarded as being established, accepted, or self-evidently true.  
- $A$: set or event  
- Empty set: $\phi$
- For any event $A$, $0 \le P(A) \le 1 $
- $P(S) = 1$
- If $A_{1}, A_{2} ... A_{n}$ are a collection of mutually exclusive (disjoint) events, then the probability of the union of those events equals the sum of the individual probabilities.  
 if $P(A) = 0.20$ and $P(B) = 0.15$, then $P(A \cup B) = 0.35$  
$P(\cup_{n}^{k=1} A_{k}) = \displaystyle\sum_{k=1}^n P(A_{k})$ 

Based off the above:  
- $A \cup A^{c} = S$  
- $A \cap A^{c} = \phi$ 
- $P(A^{c}) = 1-P(A) 
- if $A \cap B = 0$, then $P(A \cap B) = 0$ 
- $P(A \cup B) = P(A) + P(B) - P(A \cup B)$


## Basic probability operations
`multiplication rule`:  used to find the probability of two events happening at the same time $P(A \cap B) = P(A) ⋅ P(B)$. For a combination of k objects that have n options: $n_{1} ⋅ n_{2} ⋅ ... ⋅ n_{k} = n^{k}$  

`factorial`: number of combinations for k objects that have n options where n options cannot be reused ('replaced'): 
$ {n ⋅ (n-1) ⋅ ... ⋅ (n-k) = \frac{n!}{k!}}$  
`binomial coefficient` : 'n choose k' ${n \choose k} = \frac{n!}{(n-x)!x!}$ : for all combinations of n ($n!$), 
divide out options exceeding the number of choices required ($n-k$)! and remove permutations (x!)  (options that have the same choices in diffferent orders)  
`Bose-Einstein result`: pick $k$ objects from set of size $n$ with replacement, and order does not matter (objects in set are not unique)
 n identical objects can be divided into r groups where each group can have any number of objects, including 0


### Sampling table

|                  | order matters         | order does not matter |
|------------------|-----------------------|-----------------------|
| with replacement | $n^{k}$               | $n+k-1 \choose k$     |
| w/o replacement  | $\frac {n!} {(n-k!)}$ | $n \choose k$         |


<details>
  <summary> Example: ordered sampling, with replacement</summary>

> How many permutations of a 4-digit number can be made (e.g. dial lock), where each digit can be sampled from [0-9] with replacement, where order matters
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
> - the unique ways can 3 indices (locations) in the sequence be chosen for the A to be in (all combination of 3 unique locations)
> - the unique ways can 4 indices in the sequence be chosen for the B to be in (all combination of 4 unique locations)
> - the locations are unique ("without replacement", but the order in which they are selected does not matter: indices [1, 3, 4] = indices [4, 3, 1] = BABAABB (assuming a 0 index)
> - choose 4 from 7 $P_{k,n}$

</details>

<br>

<details>

  <summary> Example: unordered sampling, with replacement</summary>

> How many "combinations" of a 4-digit number (e.g. button lock) can be made, where each digit can be sampled from [0-9], order does not matter
> - order of selecting the four digits does not matter 
> - sample 4 items from 10 options, replacing without removing the selected value from the set of 10. how many different samples can be taken?
> 
> The ball and box metaphor
> - how many of each digit are in the sample (always sum to k/sample size). $i_{0} + i_{1} + i_{2} + ... + i_{9} = 4; i \in \mathbb{Z}_+$
> - How many answers are there to the above equation?
> - How many ways can four "balls" (the unordered digits) be re-arranged between 10 "containers"?  
> `| ⊛⊛⊛⊛ |   |   |   |   |   |   |   |   |   |`  
> `| ⊛⊛⊛  | ⊛ |   |   |   |   |   |   |   |   |` 
> - in the top example, all four digits are in the first box, so the lock combination  is "0 0 0 0", in the next, any permutation of "1 0 0 0"
> - how many times can the positions of the internal "container walls `|`" and the "balls `⊛`" be rearranged?
> - simple unordered sampling without replacement: selecting four unique indices from a possible 13 (there cannot be any balls outside the box, the the external walls are not counted)  

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
$$  1 = P(A)⋅P(B^{c})  + P(A)⋅P(B) + P(A^{c})⋅P(B^{c}) + P(A^{c})⋅P(B) $$  



<br>

<details>

  <summary> Example</summary>


> What is the probability that Anne will walk to work, if P(walk) is .95 when not raining, and P(walk) is .3 when raining, and P(raining) is .4  
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



<br>
<br>

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
`19`  $x=⟨x1,x2,…,xn⟩	\mathbf{x} = \langle x_{1}, x_{2}, \dots, x_{n}\rangle$  
`20`  $x \in A$  
`21`  $|A|$  
`22`  $x \in A$  
`23`  $x \subset B$  
`24`  $x \subseteq B$  
`25`  $A \cup B$  
`26`  $A \cap B$  
`27`  $X \sim {\sf Binom}(n, \pi)$ (sf for “slide font”)  
`28`  $\mathrm{P}(X \le x) = {\tt pbinom}(x, n, \pi)$ (tt for “typewriter type”)  
`29`  $P(A \mid B)$  
`30`  $\mathrm{P}(A \mid B)$ (mathrm for “math roman font”  
`31`  $\{1, 2, 3\}$  
`32`  $\sin(x)$
`33`  $\log(x)$  
`34`  ∫ba	$\int_{a}^{b}$  
`35`  $\left(\int_{a}^{b} f(x) \; dx\right)$  
`36`  $\left[\int_{-\infty}^{\infty} f(x) \; dx\right]$  
`37`  $\left. F(x) \right|_{a}^{b}$  
`38`  $\sum_{x = a}^{b} f(x)$  
`39`  $\prod_{x = a}^{b} f(x)$  
`40`  $\lim_{x \to \infty} f(x)$  
`41`  $\displaystyle \lim_{x \to \infty} f(x)$  
`42`  $ \ne $  
`43` # Greek Letters  
`44`  αA: $\alpha A$	νN	$\nu N$  
`45`  βB: $\beta B$	ξΞ	$\xi\Xi$  
`46`  γΓ: $\gamma \Gamma$	oO	$o O$ (omicron)  
`47`  δΔ: $\delta \Delta$	πΠ	$\pi \Pi$  
`48`  ϵεE: $\epsilon \varepsilon E$	ρϱP	$\rho\varrho P$  
`49`  ζZ: $\zeta Z \sigma \,\!$	Σ	$\sigma \Sigma$  
`50`  ηH: $\eta H$	τT	$\tau T$  
`51`  θϑΘ: $\theta \vartheta \Theta$	υΥ	$\upsilon \Upsilon$  
`52`  ιI: $\iota I$	ϕφΦ	$\phi \varphi \Phi$  
`53`  κK: $\kappa K$	χX	$\chi X$ λΛ: $\lambda \Lambda$	ψΨ	$\psi \Psi$ μM: $\mu M$	ωΩ	$\omega \Omega$

