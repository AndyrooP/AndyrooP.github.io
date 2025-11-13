---
layout: post
title: "The growth of entire functions and their zeros"
date: 2022-7-24 12:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og\_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Clearly the function \\(f(z)=e^z\\) is an entire function that satisfies \\(f(\log{n})=n\\) for every \\(n\in\mathbb{N}\\). Are there any other such entire functions?

The answer is no if we insist that \\(f\\) does not grow "too quickly". We can show this by studying the relationship between the growth of an entire function and the distribution of its zeros. The fundamental result in this theory is <a href="https://en.wikipedia.org/wiki/Jensen%27s_formula" target="_blank">_Jensen's formula_</a>.

**Theorem (Jensen's formula):** Let \\(f\colon G\to\mathbb{C}\\) be holomorphic with \\(\overline{B\_r(0)}\subseteq G\\). Let \\(a\_1,\dots,a\_n\\) be zeros of \\(f\\) in \\(B\_r(0)\\) and suppose \\(f(0)\neq0\\). Then,
\\[\log{\|f(0)\|}+\sum\_{k=1}^{n}{\log{\frac{r}{\|a\_k\|}}}=\frac{1}{2\pi}\int\_{0}^{2\pi}{\log{\|f(re^{it})\|}\ \mathrm{d}t}.\\]
​
Jensen's formula tells us that the distribution of the zeros of an entire function is controlled by the growth of the function in the following sense.

**Corollary:** Let \\(f\colon\mathbb{C}\to\mathbb{C}\\) be an entire function with \\(f(0)=1\\). For ever \\(r>0\\), let \\(N(r)\\) denote the number of zeros of \\(f\\) in the ball \\(B\_r(0)\\) and let \\(M(r):=\sup\_{z\in B\_r(0)}{\|f(z)\|}\\). Then, for every \\(r>0\\),
\\[N(r)\log{2}\leq\log{M(2r)}.\\]
​
_Proof_: Pick \\(r>0\\). Let \\(a\_1,\dots,a\_n\\) be the roots of \\(f\\) in \\(B\_{2r}(0)\\). Observe that \\(\log{\left\|\frac{2r}{a\_k}\right\|}>0\\) for each \\(k\\) by construction. Hence, by Jensen's formula,
\\[\log{M(2r)}\geq\frac{1}{2\pi}\int\_{0}^{2\pi}{\log{\|f(2re^{it})\|\ \mathrm{d}t}}=\log{\|f(0)\|}+\sum\_{k=1}^{n}{\log{\left\|\frac{2r}{a\_k}\right\|}}=\sum\_{k=1}^{n}{\log{\left\|\frac{2r}{a\_k}\right\|}}.\\]
We can break up the sum on the right hand side by considering the indices \\(k\\) for which \\(\|a\_k\|<r\\) and the indices \\(k\\) for which \\(r\leq\|a\_k\|<2r\\). This gives us
\\[\sum\_{k=1}^{n}{\log{\left\|\frac{2r}{a\_k}\right\|}}=\sum\_{\|a\_k\|<r}{\log{\left\|\frac{2r}{a\_k}\right\|}}+\sum\_{r\leq\|a\_k\|<2r}{\log{\left\|\frac{2r}{a\_k}\right\|}}\geq \sum\_{\|a\_k\|<r}{\log{\left\|\frac{2r}{a\_k}\right\|}}\geq N(r)\log{2},\\]
​with the inequalities coming from the fact that the terms in the first sum are at least \\(\log{2}\\) and the terms in the second sum are positive. \\(\square\\)

This corollary leads to another way in which the growth of an entire function controls the distribution of the zeros. Let \\(f\\) be an entire function. Suppose \\(f\\) has the nonzero roots \\(\\{a\_n\\}\_{n\in S}\\), where \\(S\\) is finite or countable. The _critical exponent_ of \\(f\\), denoted \\(\alpha\\), is defined to be
\\[\alpha:=\inf{\left\\{t>0\colon\sum\_{n\in S}{\frac{1}{\|a\_n\|^t}}<\infty\right\\}}.\\]
Clearly, \\(\alpha\\) quantifies the distribution of the zeros of \\(f\\) by measuring how quickly the roots of \\(f\\) grow: the larger \\(\alpha\\) is, the slower the roots of \\(f\\) must grow. Notice that it is very simple to see that if \\(S\\) is countable, then for any \\(\epsilon>0\\), we have \\(\sum\_{n\in S}{\frac{1}{\|a\_n\|^{\alpha+\epsilon}}}<\sum\_{n\in S}{\frac{1}{\|a\_n\|^{\alpha-\epsilon}}}=\infty\\). Hence, \\(\alpha\\) is another way to quantify the rate of decay of the terms of a series. While the behavior of the series is easy to understand when we take powers above and below \\(\alpha\\), it is unclear what actually happens when the power is exactly \\(\alpha\\). In fact, the series may either converge or diverge when we take the power to be exactly \\(\alpha\\). This is another sense in which <a href="http://localhost:4000/bay/2022/07/12/Minimal-Rate-of-Decay-of-Convergent-Series" target="_blank">the barrier between convergent and divergent series is fuzzy</a>.

​Now, suppose \\(f\\) is an arbitrary entire function. We define the <a href="https://en.wikipedia.org/wiki/Entire_function#Order_and_type" target="_blank">_order_</a> of \\(f\\), denoted \\(\lambda\\), to be
\\[\lambda:=\limsup\_{r\to\infty}{\frac{\log{\log{M(r)}}}{\log{r}}}.\\]
Clearly, \\(\lambda\\) is a measure of how quickly \\(f\\) grows. In particular, \\(\lambda\\) detects "exponentially polynomial" growth. That is, the order of the entire function \\(\exp{z^d}\\) is \\(d\\). The order of any polynomial is simply zero. It is fairly straightforward to show that order of a sum or product of entire functions is at most the maximal order of the addends or factors, respectively.

There is a relationship between the critical exponent and the order of an entire function. This result is morally identical to our corollary: the distribution of the zeros of an entire function is controlled by the growth of the function.

**Proposition:** ​Let \\(f\\) be an entire function with critical exponent \\(\alpha\\) and order \\(\lambda\\). Then, \\(\alpha\leq\lambda\\).

_Proof_: It is clear that the order and critical exponent of an entire function is invariant under multiplication of the function by a nonzero constant, so we may assume without loss of generality that \\(f(0)=1\\). First, note that when \\(f\\) has finitely many zeros, we have \\(\alpha=0\\) and the conclusion is immediate. So it suffices to assume that \\(f\\) has countably many zeros. Suppose that the zeros of \\(f\\) are \\(a\_1,a\_2,\dots\\) where \\(\|a\_1\|\leq\|a\_2\|\leq\dots\\). Note that \\(\|a\_n\|\to\infty\\) since otherwise \\(f\\) must be the constant zero function which contradicts our assumption that \\(f\\) has countably many roots. Then by the corollary, for every \\(n\in\mathbb{N}\\) we have
\\[n-1\leq N(\|a\_n\|)\leq \frac{\log{M(2\|a\_n\|)}}{\log{2}}.\\]
Pick \\(\epsilon>0\\). By the definition of order, there exists \\(R\\) so large that \\(\log{M(r)}\leq r^{\lambda+\frac{\epsilon}{2}}\\) for all \\(r>R\\). Since \\(\|a\_n\|\to\infty\\), we have that there exists \\(N\\) so that for every \\(n>N\\) we have
\\[n-1\leq N(\|a\_n\|)\leq \frac{\log{M(2\|a\_n\|)}}{\log{2}}\leq\frac{(2\|a\_n\|)^{\lambda+\frac{\epsilon}{2}}}{\log{2}}.\\]
Rearranging this inequality we obtain
\\[\frac{1}{\|a\_n\|}\leq \frac{2}{[(n-1)\log{2}]^{\frac{1}{\lambda+\frac{\epsilon}{2}}}}.\\]
Therefore,
\\[\frac{1}{\|a\_n\|^{\lambda+\epsilon}}\leq\frac{2^{\lambda+\epsilon}}{[(n-1)\log{2}]^{\frac{\lambda+\epsilon}{\lambda+\frac{\epsilon}{2}}}}.\\]
Since \\(\frac{\lambda+\epsilon}{\lambda+\frac{\epsilon}{2}}>1\\), we have that
\\[\sum\_{n=N+1}^{\infty}{\frac{1}{\|a\_n\|^{\lambda+\epsilon}}}\leq\sum\_{n=N+1}^{\infty}{\frac{2^{\lambda+\epsilon}}{[(n-1)\log{2}]^{\frac{\lambda+\epsilon}{\lambda+\frac{\epsilon}{2}}}}}<\infty.\\]
Therefore, \\(\sum\_{n=1}^{\infty}{\frac{1}{\|a\_n\|^{\lambda+\epsilon}}}<\infty\\) so that \\(\lambda+\epsilon\geq\alpha\\). Since \\(\epsilon\\) was arbitrary, the conclusion follows. \\(\square\\)

Notice that in our proof above, we used the fact that if the \\(a\_n\\) were not unbounded, \\(f\\) must be the constant zero function. This essentially due to the <a href="https://en.wikipedia.org/wiki/Bolzano%E2%80%93Weierstrass_theorem" target="_blank">Bolzano-Weierstrass theorem</a>, which would guarantee that there the zeros of \\(f\\) have a limit point, from which it follows by the <a href="https://en.wikipedia.org/wiki/Identity_theorem" target="_blank">identity theorem</a> that \\(f\\) is the constant zero function. This subtle point makes a reappearance in our main result, which we are now able to state.

**Theorem:** Let \\(f\\) and \\(g\\) be entire functions with order at most \\(\delta<\infty\\). Suppose that \\(\\{a\_n\\}\_{n\in\mathbb{N}}\\) is a sequence of nonzero complex numbers such that \\(f(a\_n)=g(a\_n)\\) for every \\(n\in\mathbb{N}\\) and
\\[\sum\_{n=1}^{\infty}{\frac{1}{\|a\_n\|^{1+\delta}}}<\infty.\\]
​Then, \\(f=g\\).

_Proof_: ​Consider the entire function \\(F=f-g\\). Let \\(0\\) be a root of \\(F\\) with multiplicity \\(m\\). Then we can write \\(F=z^mG\\) for some entire function \\(G\\) where \\(G(0)\neq0\\) but \\(G(a\_n)=0\\) for every \\(n\\). Let \\(\lambda\\) be the order of \\(G\\).

We know that \\(\lambda\leq\delta\\) since the order of a sum is at most the maximal order of the addends. By the condition given on \\(\\{a\_n\\}\_{n\in\mathbb{N}}\\), we have \\(\lambda+1\leq\delta+1\leq\alpha\\) where \\(\alpha\\) is the critical exponent of \\(G\\). But by the previous proposition, we also have \\(\alpha\leq\lambda\\), hence we have \\(\lambda+1\leq\lambda\\), contradicting our assumption that \\(\delta\\) is finite.

So where is the mistake? The error is in assuming that the critical exponent of \\(G\\) is well-defined to begin with. Recall that the definition of the critical exponent requires the entire function to have at most countably many roots. Hence, \\(G\\) must have have uncountably many roots. Now it is simple to show that \\(G\\) must be the constant zero function. We may reason as follows.

Since \\(\mathbb{C}\\) is \\(\sigma\\)-compact, we can let \\(\\{S\_n\\}\_{n\in\mathbb{N}}\\) be a countable collection of compact subsets of \\(\mathbb{C}\\) such that \\(\mathbb{C}=\bigcup\_{n\in\mathbb{N}}{S\_n}\\) (one can choose, for example, closed unit squares). Let \\(Z\subseteq\mathbb{C}\\) be the zero set of \\(G\\). Suppose \\(Z\cap S\_n\\) is finite for every \\(n\in\mathbb{N}\\). Then \\(Z=\bigcup\_{n\in\mathbb{N}}{(Z\cap S\_n)}\\) is countable as a countable union of finite sets, which contradicts our observation that \\(Z\\) is uncountable. Hence, there exists \\(N\in\mathbb{N}\\) such that \\(Z\cap S\_N\\) is infinite. But since \\(S\_N\\) is compact, it is sequentially compact, and thus \\(Z\cap S\_N\\) has a limit point in \\(S\_N\\). In particular, \\(Z\\) has a limit point so \\(F\\) is identically zero. \\(\square\\)

​This is a great example of why it is very important to check the hypotheses of not just theorems, propositions, and lemmas, but also definitions!

The theorem essentially tells us the following. Suppose \\(f\\) is an entire function with order \\(\lambda\\) and zeros \\(\\{a\_n\\}\_{n\in\mathbb{N}}\\). If \\(f\\) grows too slowly (that is, \\(\lambda\\) is small) and the zeros of \\(f\\) do not grow very quickly (that is, \\(\frac{1}{\|a\_n\|}\\) does not decay rapidly), then \\(f\\) is the constant zero function. We can use this idea to show that if \\(g(z)=e^z\\), and \\(f\\) is an entire function of _finite order_ such that \\(f(\log{n})=n\\) for all \\(n\in\mathbb{N}\\), the entire function \\(f-g\\) is the constant zero function. In essence, we will show that if \\(f\\) does not grow too quickly, the roots \\(\log{n}\\) grow so slowly that the assumption that \\(f\\) is entire forces \\(f(z)-e^z\\) to be identically zero.

Let \\(g(z)=e^z\\). Suppose \\(f\\) is an entire function of finite order such that \\(f(\log{n})=n\\) for all \\(n\in\mathbb{N}\\). \\(g\\) is of order \\(1\\) and agrees with \\(f\\) on \\(\\{\log{n}\\}\_{n\in\mathbb{N}}\\). Let \\(\lambda\_f\\) be the order of \\(f\\) and \\(\delta=\max{(1,\lambda\_f)}\\). Notice that the orders of \\(f\\) and \\(g\\) are at most \\(\delta<\infty\\).

Observe that if we apply L'hôpital's rule \\(\left\lfloor 1+\delta\right\rfloor\\) times, we obtain that
\\[\lim\_{x\to\infty}{\frac{x}{(\log{x})^{1+\delta}}}=\lim\_{x\to\infty}{\frac{x}{\left\lfloor 1+\delta\right\rfloor!(\log{x})^{\\{\delta\\}}}}\geq\frac{1}{\left\lfloor 1+\delta\right\rfloor!}\lim\_{x\to\infty}{\frac{x}{\log{x}}}=\infty,\\]
where \\(\\{\delta\\}\\) is the fractional part of \\(\delta\\) and the last equality follows from one more application of L'hôpital's rule. So \\(\lim\_{x\to\infty}{\frac{x}{(\log{x})^{1+\delta}}}=\infty\\). This means there exists some \\(N\in\mathbb{N}\\) so that for all \\(n>N\\), we have \\(n>(\log{n})^{1+\delta}\\) so that \\(\frac{1}{n}<\frac{1}{(\log{n})^{1+\delta}}\\). Since the harmonic series \\(\sum\_{n=1}^{\infty}{\frac{1}{n}}\\) diverges, we note that by direct comparison,
\\[\sum\_{n=2}^{\infty}{\frac{1}{\|\log{n}\|^{1+\delta}}}=\infty.\\]
Now by the previous theorem, it must be true that \\(f=g\\). So there is only one function \\(f\\) that can exist as described, and it is \\(f(z)=e^z\\).

Note that the assumption that \\(f\\) has finite order is crucial. Often, in these types of arguments, one really needs some control over the growth of the entire function being studied. I am not sure if much can be said if we remove the requirement that \\(f\\) must have finite order.

This theory can be pushed farther. The growth of the zeros of an entire function can be quantified in way distinct from the critical exponent. The quantity that does this is known as the <a href="https://en.wikipedia.org/wiki/Entire_function#Genus" target="_blank">_genus_</a> of the entire function, and it is somewhat related to the critical exponent. If we denote the genus of an entire function as \\(h\\) and the order of the function as \\(\lambda\\), then it is true that \\(h\leq\lambda\leq h+1\\). This is a pretty strong relationship: it gives us a very good understanding of the growth of an entire function given the growth of its zeros. This result can be used to prove weak versions of the <a href="https://en.wikipedia.org/wiki/Picard_theorem" target="_blank">Picard theorems</a>, which I think are some of the most interesting results in complex analysis.