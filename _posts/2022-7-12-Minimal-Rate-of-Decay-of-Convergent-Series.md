---
layout: post
title: "There is no minimal rate of decay on the terms of a convergent series"
date: 2022-7-12 12:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og\_image: /assets/img/content/post-example/Banner.jpg
math: true
---

In high school calculus, one is often inundated with various series convergence tests. It is often a headache to determine which convergence test to use on a particular series. None of the high school convergence tests work on every series. For example,

* The ratio test is inconclusive if the limit of the ratio of consecutive terms is \\(1\\).
* The integral test does not say anything about the convergence of series whose terms are not monotone decreasing.
* The limit comparison test is inconclusive if the limit of the ratio of the terms of the two series is zero.

This may lead one to wonder: is there a convergence test that works on every series?

The answer is no. <a href="https://math.stackexchange.com/questions/3454608/is-there-always-exist-counterexamples-for-known-convergence-tests/3454623#3454623" target="_blank">A short and clever argument</a> shows that an algorithm that can determine if any sequence (or equivalently, series) converges would be capable of solving the <a href="https://en.wikipedia.org/wiki/Halting_problem" target="_blank">halting problem</a>, and thus no such algorithm can exist. This result may be disappointing to high school math students. It also suggests that any notion of a "barrier" between the convergent series and the divergent series would be fuzzy at best. There are many ways to define what such a threshold could be. Intuitively, we would like to say that the threshold is some "critical rate of decay" on the terms of series (modulo trivial modifications to the series) such that a series converges if and only if the rate of decay of the terms of that series is at least the critical rate of decay. There are several different ways of making this precise. We will discuss the following way.

**Definition:** Let \\(\\{a\_n\\}\_{n\in\mathbb{N}}\\) be a sequence of positive numbers. The series \\(\sum\_{n=1}^{\infty}{a\_n}\\) is said to be a **threshold series​** (and the sequence \\(\\{a\_n\\}\_{n\in\mathbb{N}}\\) is a **threshold sequence**) if \\(\sum\_{n=1}^{\infty}{a\_n\|c\_n\|}<\infty\\) if and only if the sequence \\(\\{c\_n\\}\_{n\in\mathbb{N}}\\) is bounded.

Indeed, this notion of a threshold series captures what we intuitively want. Of course, modifying the terms of any series by any collection of bounded coefficients will not change the convergence of the series. Our notion of threshold series thus includes all such modifications (this is what we meant by quantifying a rate of decay of the terms of a series modulo trivial modifications). The main point is that modification by an unbounded collection of coefficients will always tip the threshold series over the edge into the realm of divergent series—no matter how slowly our coefficients grow. Thus, a threshold series is a series that exhibits a "critical rate of decay" in its terms.

It turns out that our hunch that the barrier between convergent and divergent series is fuzzy is correct in the sense that threshold series do not exist. To prove this result, we will need the following lemma.

**Lemma:** Let \\(X\\) and \\(Y\\) be topological spaces and let \\(\Omega\\) be a dense subset of \\(Y\\). If \\(\varphi\colon X\to Y\\) is an open map, then \\(\varphi^{-1}(\Omega)\\) is dense in \\(X\\).

_Proof_: Pick \\(x\in X\\) and an open neighborhood \\(U\\) of \\(x\\). Since \\(\varphi\\) is an open map and \\(U\\) is nonempty, \\(\varphi(U)\\) is an open subset of \\(Y\\). Since \\(\Omega\\) is dense, there exists \\(y\in\varphi(U)\cap\Omega\\). In particular, since \\(y\in\varphi(U)\\), there exists \\(x'\in U\\) such that \\(\varphi(x')=y\in\Omega\\). Hence, \\(x'\in\varphi^{-1}(\Omega)\\), so \\(U\cap\varphi^{-1}(\Omega)\\) is nonempty. \\(\square\\)

​Now we may proceed with our main argument. We will reason by contradiction. Suppose that there exists a threshold sequence \\(\\{a\_n\\}\_{n\in\mathbb{N}}\\). Let \\(B(\mathbb{N})\\) be the space of bounded functions on \\(\mathbb{N}\\). We can interpret \\(B(\mathbb{N})\\) as a Banach space with the uniform norm (i.e. the supremum norm). Let \\(\mu\\) be the counting measure on \\(\mathbb{N}\\) so that \\(L^1(\mu)\\) is precisely the collection of absolutely convergent sequences. Define the map \\(T\colon B(\mathbb{N})\to L^1(\mu)\\) given by \\((Tf)(n)=a\_nf(n)\\) for every \\(n\in\mathbb{N}\\) and \\(f\in B(\mathbb{N})\\). Note that the image of \\(T\\) is a subset of \\(L^1(\mu)\\) and so \\(L^1(\mu)\\) is a valid codomain because \\(\\{a\_n\\}\_{n\in\mathbb{N}}\\) is a threshold sequence. It is trivial to check that \\(T\\) is a surjective linear map between Banach spaces.

​Suppose that we have a sequence of functions \\(\\{g\_n\\}\_{n\in\mathbb{N}}\subseteq B(\mathbb{N})\\) such that \\(g\_n\to g\\) and \\(Tg\_n\to h\\) where the convergence occurs with respect to the norms of the relevant Banach spaces. Pick \\(\epsilon>0\\) and fix \\(k\in\mathbb{N}\\). Since \\(g\_n\to g\\) in uniform norm, we have that \\(g\\) is the pointwise limit of the \\(g\_n\\). In particular, we may pick \\(N\_1\\) so large that for all \\(n>N\_1\\) we have \\(|g\_n(k)-g(k)|<\frac{\epsilon}{2a\_k}\\). Since \\(Tg\_n\to h\\) in the \\(L^1\\) norm, we pick \\(N\_2\\) so large that for all \\(n>N\_2\\) we have
\\[|a\_kg\_n(k)-h(k)|\leq\sum\_{j=1}^{\infty}{|a\_jg\_n(j)-h(j)|}=\sum\_{j=1}^{\infty}{|Tg\_n(j)-h(j)|}=\|Tg\_n-h\|\_1<\frac{\epsilon}{2}.\\]
Now, for \\(n>\max{(N\_1,N\_2)}\\), we have
\\[\begin{split}
|(Tg)(k)-h(k)|&=|a\_kg(k)-h(k)|\\\\\
&=|a\_kg(k)-a\_kg\_n(k)+a\_kg\_n(k)-h(k)|\\\\\
&\leq|a\_kg(k)-a\_kg\_n(k)|+|a\_kg\_n(k)-h(k)|\\\\\
&<\frac{\epsilon}{2}+\frac{\epsilon}{2}=\epsilon.
\end{split}\\]
Since \\(\epsilon\\) is arbitrary, we have that \\((Tg)(k)=h(k)\\). Thus, \\(Tg=h\\). We have showed that \\(T\\) is a closed linear map, hence \\(T\\) is continuous by the closed graph theorem. Now since \\(T\\) is a surjective continuous linear map, \\(T\\) is open by the open mapping theorem. Let us define
\\[S=\left\\{f\in B(\mathbb{N}): \left|f^{-1}(\mathbb{R}\setminus\\{0\\})\right|<\infty\right\\}.\\]
It is clear that \\(T^{-1}(S)=S\\). Notice that for any \\(f\in S\\), if \\(\chi\_{\mathbb{N}}\in B(\mathbb{N})\\) is the constant indicator function,
\\[\sup\_{n\in\mathbb{N}}{|\chi\_{\mathbb{N}}(n)-f(n)|}\geq\sup\_{n\in f^{-1}(\\{0\\})}{|\chi\_{\mathbb{N}}(n)-f(n)|}=1.\\]
Hence, \\(S\\) is not dense in \\(B(\mathbb{N})\\). Now pick \\(\epsilon>0\\) and \\(f\in L^1(\mu)\\). By definition, \\(\sum\_{n=1}^{\infty}{|f(n)|}<\infty\\), so we may pick \\(N\\) so large that for \\(m\geq N\\) we have \\(\sum\_{n=m}^{\infty}{|f(n)|}<\epsilon\\). Define the function \\(g\\) by
\\[g(n)=\begin{cases}
f(n) & n<N\\\\\
0 & n\geq N.
\end{cases}\\]
Note that \\(g\in S\\) by construction. Moreover,
\\[\|f-g\|\_1=\sum\_{n=1}^{\infty}{|f(n)-g(n)|}=\sum\_{n=N}^{\infty}{|f(n)|}<\epsilon.\\]
This means that \\(S\\) is dense in \\(L^1(\mu)\\). So \\(S\\) is dense in \\(L^1(\mu)\\) but not \\(B(\mathbb{N})\\) and \\(T\colon B(\mathbb{N})\to L^1(\mu)\\) is an open map with \\(T^{-1}(S)=S\\). This contradicts the lemma, completing the argument.

​This is one of my favorite problems because it provides some insight to something I've always thought about when I was younger (the "barrier" between convergent and divergent series) using some comparatively abstract techniques from functional analysis. A lot was swept under the rug via the open mapping and closed graph theorems. I find it fascinating that these abstract results can tell us something that I find relatively tangible about series.

The problem of measuring how quickly the terms of a series decay isn't just one from my big bag of problems that I find interesting. It is in fact well-studied in complex analysis, where many results are known regarding how quickly the zeros of an entire function grow. Allegedly, this has significant ramifications in analytic number theory. At some point in the future, I will talk about the _critical exponent_ and the _order_ of an entire function and the relationship between the growth of an entire function and the distribution of its zeros.