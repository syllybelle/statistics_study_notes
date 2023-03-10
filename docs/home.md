#### Course notes

#### University of Colorado Boulder

# Probability Theory: Foundation for Data Science

<hr/>

An amalgamation of the course-work, the textbook, and my own research stemming from confusion along the way.
Coming from a non-stats background, currently working as a dataish scientist.
Includes some forays into R from the perspective of a python native, because all the course material is in R

?> [coursera course](https://www.coursera.org/learn/probability-theory-foundation-for-data-science/)  
[Textbook](https://bookdown.org/probability/beta/)

<hr/> 

_my understanding of Coursera's [acceptable use policy](https://www.coursera.org/about/terms#acceptable-use-policy) is
that personal notes are fine to share, as long as it is not lifting the content. As this is an amalgamation of the
textbook the course, and my own interpretations, as far as I am aware I am not violating the copywrite of either the
textbook or the Coursera course, but if anyone knows otherwise, please flag it as an issue._

<hr/> 

# Misc resources I'm using for the generation of these docs

Playing around with docsify also counts as professional development, right...

## Markdown & docsify cheatsheats:

?> [Singapore gov](https://katex.org/docs/support_table.html) _wtf, for real, though_  
[markdown guide](https://www.markdownguide.org/cheat-sheet/)  
[docsify](https://docsify.js.org/#/?id=docsify)

## Symbols and operators

?> from [katex](https://katex.org/docs/support_table.html) package


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
`19  $x=???x1,x2,???,xn??? \mathbf{x} = \langle x_{1}, x_{2}, \dots, x_{n}\rangle$` $x=???x1,x2,???,xn??? \mathbf{x} = \langle x_{1}, x_{2}, \dots, x_{n}\rangle$
`20  $x \in A$` $x \in A$  
`21  $|A|$` $|A|$  
`22  $x \in A$` $x \in A$  
`23  $x \subset B$` $x \subset B$  
`24  $x \subseteq B$` $x \subseteq B$  
`25  $A \cup B$` $A \cup B$  
`26  $A \cap B$` $A \cap B$  
`27  $X \sim {\sf Binom}(n, \pi)$ (sf for ???slide font???)` $X \sim {\sf Binom}(n, \pi)$ (sf for ???slide font???)  
`28  $\mathrm{P}(X \le x) = {\tt pbinom}(x, n, \pi)$ (tt for ???typewriter type???)` $\mathrm{P}(X \le x) = {\tt pbinom}(x, n, \pi)$ (tt for ???typewriter type???)  
`29  $P(A \mid B)$` $P(A \mid B)$  
`30  $\mathrm{P}(A \mid B)$ (mathrm for ???math roman font???` $\mathrm{P}(A \mid B)$ (mathrm for ???math roman font???  
`31  $\{1, 2, 3\}$` $\{1, 2, 3\}$  
`32  $\sin(x)$` $\sin(x)$
`33  $\log(x)$` $\log(x)$  
`34  ???ba $\int_{a}^{b}$` ???ba $\int_{a}^{b}$  
`35  $\left(\int_{a}^{b} f(x) \; dx\right)$` $\left(\int_{a}^{b} f(x) \; dx\right)$  
`36  $\left[\int_{-\infty}^{\infty} f(x) \; dx\right]$` $\left[\int_{-\infty}^{\infty} f(x) \; dx\right]$  
`37  $\left. F(x) \right|_{a}^{b}$` $\left. F(x) \right|_{a}^{b}$  
`38  $\sum_{x = a}^{b} f(x)$` $\sum_{x = a}^{b} f(x)$  
`39  $\prod_{x = a}^{b} f(x)$` $\prod_{x = a}^{b} f(x)$  
`40  $\lim_{x \to \infty} f(x)$` $\lim_{x \to \infty} f(x)$  
`41  $\displaystyle \lim_{x \to \infty} f(x)$` $\displaystyle \lim_{x \to \infty} f(x)$  
`42 `
`43 # Greek Letters`  Greek Letters  
`44  ??A: $\alpha A$ ??N $\nu N$` ??A: $\alpha A$ ??N $\nu N$  
`45  ??B: $\beta B$ ???? $\xi\Xi$` ??B: $\beta B$ ???? $\xi\Xi$  
`46  ????: $\gamma \Gamma$ oO $o O$ (omicron)` ????: $\gamma \Gamma$ oO $o O$ (omicron)  
`47  ????: $\delta \Delta$ ???? $\pi \Pi$` ????: $\delta \Delta$ ???? $\pi \Pi$  
`48  ????E: $\epsilon \varepsilon E$ ????P $\rho\varrho P$` ????E: $\epsilon \varepsilon E$ ????P $\rho\varrho P$  
`49  ??Z: $\zeta Z \sigma \,\!$ ?? $\sigma \Sigma$` ??Z: $\zeta Z \sigma \,\!$ ?? $\sigma \Sigma$  
`50  ??H: $\eta H$ ??T $\tau T$` ??H: $\eta H$ ??T $\tau T$  
`51  ??????: $\theta \vartheta \Theta$ ???? $\upsilon \Upsilon$` ??????: $\theta \vartheta \Theta$ ???? $\upsilon \Upsilon$  
`52  ??I: $\iota I$ ?????? $\phi \varphi \Phi$` ??I: $\iota I$ ?????? $\phi \varphi \Phi$  
`53  ??K: $\kappa K$ ??X $\chi X$ ????: $\lambda \Lambda$ ???? $\psi \Psi$ ??M: $\mu M$ ???? $\omega \Omega$` ??K: $\kappa K$ ??X $\chi X$ ????: $\lambda \Lambda$ ???? $\psi \Psi$ ??M: $\mu M$ ???? $\omega \Omega$

[//]: # (# test)

[//]: # ()

[//]: # (> An awesome project.  )

[//]: # (> )

[//]: # (`c&#40;a, b, ..&#41;`:         combine/concat/create vector/list from items a, b, ..  )

[//]: # (`character&#40;a&#41;`: convert `a` to string, or convert iterations in an interable to string type  )

[//]: # (`rbind&#40;&#41;`:     add rows)

[//]: # (<!-- ImJoyPlugin: {"type": "web-worker", "hide_code_block": true, "editor_height": "200px"} -->)

[//]: # (```js)

[//]: # (api.createWindow&#40;{src:"https://gist.github.com/oeway/96cd0f99e87abbcf97d65a3605471130"}&#41;)

[//]: # (```)

[//]: # ()

[//]: # ( )

[//]: # (f<!-- ImJoyPlugin: { "type": "web-python"} -->)

[//]: # (```python)

[//]: # (from imjoy import api)

[//]: # ()

[//]: # (class ImJoyPlugin&#40;&#41;:)

[//]: # (    async def setup&#40;self&#41;:)

[//]: # (        pass)

[//]: # ()

[//]: # (    def run&#40;self, ctx&#41;:)

[//]: # (        api.alert&#40;"Hello from a python plugin"&#41;)

[//]: # ()

[//]: # (api.export&#40;ImJoyPlugin&#40;&#41;&#41;)

[//]: # (```)