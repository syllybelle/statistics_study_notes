#### Course notes
# Probability Theory: Foundation for Data Science  
  

?> [Textbook](https://bookdown.org/probability/beta/)  


<hr/> 


# Markdown & docsify cheatsheats:
?> [Singapore gov](https://katex.org/docs/support_table.html) _wtf, for real, though_  
[markdown guide](https://www.markdownguide.org/cheat-sheet/)  
[docsify](https://docsify.js.org/#/?id=docsify)  


# Symbols and operators
?> from [katex](https://katex.org/docs/support_table.html) package


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
`42` 
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





# test

> An awesome project.  
> 
`c(a, b, ..)`:         combine/concat/create vector/list from items a, b, ..  
`character(a)`: convert `a` to string, or convert iterations in an interable to string type  
`rbind()`:     add rows


<!-- ImJoyPlugin: {"type": "web-worker", "hide_code_block": true, "editor_height": "200px"} -->
```js
api.createWindow({src:"https://gist.github.com/oeway/96cd0f99e87abbcf97d65a3605471130"})
```

 
f<!-- ImJoyPlugin: { "type": "web-python"} -->
```python
from imjoy import api

class ImJoyPlugin():
    async def setup(self):
        pass

    def run(self, ctx):
        api.alert("Hello from a python plugin")

api.export(ImJoyPlugin())
```