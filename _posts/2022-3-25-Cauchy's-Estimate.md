---
layout: post
title: "Cauchy's Estimate"
date: 2022-3-25 12:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Holomorphic functions are very "rigid". One sense in which this is true is shown via Cauchy's estimate, which essentially states that a holomorphic function that is bounded must have derivatives that are not too large. Intuitively, this makes quite a bit of sense and one may ask if this is true outside of the setting of complex analysis. The answer is in the negative. Consider the family of real functions \\(f_k\colon\mathbb{R}\to\mathbb{R}\\) defined by \\(f_k(x)=\sin{kx}\\) where \\(k\in\mathbb{R}\\) is arbitrary. Clearly each \\(f_k\\) is bounded and analytic in some neighborhood of \\(0\\). Nonetheless, there is no \\(M\\) for which \\(\|f'_k(0)\|<M\\) for all \\(k\in\mathbb{R}\\) since \\(f'_k(0)=k\\) for every \\(k\in\mathbb{R}\\). So holomorphic functions are truly "rigid" in a sense that cannot be paralleled by real-analytic functions.

​To show Cauchy's estimate, one needs to first develop the basic form of the Cauchy integral formula, use that to prove that holomorphic functions are analytic, and then study the coefficients of the power series expansion of holomorphic functions. Before we do this, we need the following lemma.

**Lemma:** If \\(|z|<1\\),
\\[\int_{0}^{2\pi}{\frac{e^{is}}{e^{is}-z}\ \mathrm{d}s}=2\pi.\\]

_Proof_: We do this by the "Feynman trick" (differentiating under the integral sign, i.e. the Leibniz rule). Let \\(\varphi(s,t)=\frac{e^{is}}{e^{is}-z}\\) on \\([0,2\pi]\times[0,1]\\). Since we make the restrictions \\(|z|<1\\) and \\(|t|<1\\), we have \\(|tz|<1\\), so \\(\varphi\\) is continuously differentiable since it is the product of \\(e^{is}\\) and the closed form of the infinite geometric series with first term \\(1\\) and common ratio \\(tz\\). Define
\\[g(t)=\int_{0}^{2\pi}{\varphi(s,t)\ \mathrm{d}s}.\\]
Since \\(\varphi\\) is continuously differentiable, the fundamental theorem of calculus implies that \\(g\\) is continuously differentiable. So by the Leibniz rule,
\\[g'(t)=\int_{0}^{2\pi}{\frac{\partial}{\partial t}\varphi(s, t)\ \mathrm{d}s}=\int_{0}^{2\pi}{\frac{ze^{is}}{(e^{is}-tz)^2}\ \mathrm{d}s}.\\]
Now, one notices that \\(\frac{zi}{e^{is}-tz}\\) is an antiderivative of the integrand, and this function takes on the same value at \\(s=0\\) and \\(s=2\pi\\), hence \\(g'(t)=0\\) so \\(g\\) is a constant function. In particular,
\\[g(1)=g(0)=\int_{0}^{2\pi}{\mathrm{d}s}=2\pi,\\]
which is precisely what we wanted to show. \\(\square\\)

We are now in a position to prove the basic form of the Cauchy integral formula. This is one of the cornerstone results in all of complex analysis.

**Cauchy's Integral Formula (Baby Version):** Let \\(G\subseteq\mathbb{C}\\) be a region and let \\(f\colon G\to\mathbb{C}\\) be continuously differentiable. Suppose that \\(r>0\\) and \\(\overline{B_r(a)}\subseteq G\\). If \\(\gamma(t)=a+re^{it}\\), \\(t\in[0,2\pi]\\), then for all \\(z\in B_r(a)\\),
\\[f(z)=\frac{1}{2\pi i}\int_{\gamma}{\frac{f(w)}{w-z}\ \mathrm{d}w}.\\]

_Proof​_: We will assume without loss of generality that \\(a=0\\) and \\(r=1\\). Pick \\(z\in\mathbb{C}\\) with \\(|z|<1\\). We use a technique similar to the one used in proving the lemma. Define
\\[\varphi(s,t)=\frac{f(z(1-t)+te^{is})e^{is}}{e^{is}-z}-f(z),\\]
where \\((s,t)\in[0,2\pi]\times[0,1]\\). Since \\(\varphi\\) is continuously differentiable, so is \\(g\\), so the Leibniz rule gives us
\\[g'(t)=\int_{0}^{2\pi}{e^{is}f'(z(1-t)+te^{is})\ \mathrm{d}s}.\\]
Now we notice that \\(-\frac{i}{t}f'(z(1-t)+te^{is})\\) is an antiderivative of the integrand that takes on the same value at \\(s=0\\) and \\(s=2\pi\\). Hence, \\(g'(t)=0\\) and \\(g\\) is constant. In particular,
\\[g(1)=g(0)=f(z)\int_{0}^{2\pi}{\frac{e^{is}}{e^{is}-z}\ \mathrm{d}s}-2\pi f(z)=0,\\]
where we apply the lemma that we have proven. But \\(g(1)=0\\) is equivalent to
\\[\int_{0}^{2\pi}{\frac{f(e^{is})e^{is}}{e^{is}-z}-f(z)\ \mathrm{d}s}=0.\\]
Rearranging this gives us
\\[f(z)=\frac{1}{2\pi}\int_{0}^{2\pi}{\frac{f(e^{is})e^{is}}{e^{is}-z}\ \mathrm{d}s}.\\]
But of course, we can realize the integral on the RHS as simply \\(\frac{1}{i}\int_{\gamma}{\frac{f(w)}{w-z}\ \mathrm{d}w}\\). \\(\square\\)

We made an assumption of continuous differentiability in this theorem, but it is a classical result that <a href="https://en.wikipedia.org/wiki/Cauchy%E2%80%93Riemann_equations#Goursat's_theorem_and_its_generalizations" target="_blank">holomorphy is equivalent to this</a> (which I will not show here). Notice that the Cauchy integral formula is similar in philosophy to the mean value property of harmonic functions, which states that a harmonic function in a ball takes on its average value over the boundary of the ball at the center of the ball. For harmonic functions, the value of the function at the center of a ball is determined by the values of the function on the boundary of the ball. The Cauchy integral formula shows that holomorphic functions abide by the same principle in an even stronger sense: the value of a holomorphic function _at any point in a ball_ is completely determined by the values of the function on the boundary of the ball.

The next step is to establish that holomorphic functions are analytic by explicitly constructing a power series and showing that the power series will converge. Then, the coefficients of the power series we have constructed can be studied to control the derivatives i.e., to obtain Cauchy's estimate. By now, it should be clear that there are many parallels between holomorphic and harmonic functions, so one may try to find inspiration for the proof of the analyticity of holomorphic functions from the proof of the analyticity of harmonic functions. But a similar approach will not be possible. In the <a href="http://localhost:4000/bay/2022/02/10/Analyticity-of-Harmonic-Functions" target="_blank">proof of the analyticity of harmonic functions</a>, we essentially use a Cauchy-type estimate to control the derivatives of the harmonic function, and then use Taylor's theorem to establish the convergence of the power series. But now, we do not have access to a priori the Cauchy estimate, so we need a different approach to establish the convergence of the power series.

The solution is to realize that part of the integrand in the Cauchy integral formula can be expanded as a geometric series.

**Analyticity of Holomorphic Functions:** Let \\(f\\) be continuously differentiable in \\(B_R(a)\\). Then,
\\[f(z)=\sum_{n=0}^{\infty}{\frac{f^{(n)}(a)}{n!}(z-a)^n},\\]
and this power series has a radius of convergence of at least \\(R\\).

_Proof​_: Pick \\(r\in(0,R)\\). Let \\(\gamma(t)=a+re^{it}\\). By the Cauchy integral formula, for all \\(z\in B_r(a)\\),
\\[f(z)=\frac{1}{2\pi i}\int_{\gamma}{\frac{f(w)}{w-z}\ \mathrm{d}w}=\frac{1}{2\pi i}\int_{\gamma}{\frac{f(w)}{w-a}\left(\frac{1}{1-\frac{z-a}{w-a}}\right)\ \mathrm{d}w}.\\]
Observe that \\(|z-a|<r=|w-a|\\) since \\(w\in\\{\gamma\\}\\) and \\(z\in B_r(a)\\). Therefore, the factor of the integrand in parentheses can be realized as an infinite geometric series: \\(\frac{1}{1-\frac{z-a}{w-a}}=\sum_{n=0}^{\infty}{\left(\frac{z-a}{w-a}\right)^n}\\), and thus
\\[f(z)=\frac{1}{2\pi i}\int_{\gamma}{\sum_{n=0}^{\infty}{\frac{f(w)}{(w-a)^{n+1}}(z-a)^n}\ \mathrm{d}w}.\\]
We would like to interchange the sum and the integral. Observe that \\(\\{\gamma\\}\\) is compact and \\(|f|\\) is continuous, so \\(|f|\\) attains some maximum \\(M\\) on \\(\\{\gamma\\}\\). Moreover, \\(|w-a|=r\\). Hence,
\\[\frac{|f(w)||z-a|^n}{|w-a|^{n+1}}\leq\frac{M|z-a|^n}{r^{n+1}}=\frac{M}{r}\left(\frac{|z-a|}{r}\right)^n.\\]
Of course, since \\(|z-a|<r\\), we have that \\(\sum_{n=0}^{\infty}{\frac{|z-a|}{r}}\\) converges as a geometric series. Therefore, the Weierstrass \\(M\\)-test implies that the partial sums of \\(\sum_{n=0}^{\infty}{\frac{f(w)}{(w-a)^{n+1}}(z-a)^n}\\) converge uniformly. Since integration commutes with uniform convergence, we have
\\[f(z)=\sum_{n=0}^{\infty}{\frac{(z-a)^n}{2\pi i}\int_{\gamma}{\frac{f(w)}{(w-a)^{n+1}}\ \mathrm{d}w}}.\\]
Indeed, this is a power series that converges for \\(|z-a|<r\\). The theory of analytic functions tell us that the coefficients must actually be \\(\frac{1}{n!}f^{(n)}(a)\\). In particular, the coefficients are independent of \\(r\\). Therefore, since \\(0<r<R\\) was arbitrary, the power series above converges at least within \\(B_R(a)\\). \\(\square\\)

​The key point here was that \\(\frac{1}{z}\\) is the closed form of an infinite geometric series when \\(z\\) is in the unit disk. Indeed, a lot of complex analysis revolves around the quirks of the function \\(z\mapsto\frac{1}{z}\\).

Cauchy's estimate now follows easily. Observe that the proof above establishes that if \\(f\\) is holomorphic in the region \\(G\\) with \\(\overline{B_r(a)}\subseteq G\\) and \\(\gamma(t)=a+re^{it}\\), then \\(f^{(n)}(a)=\frac{n!}{2\pi i}\int_{\gamma}{\frac{f(w)}{(w-a)^{n+1}}\ \mathrm{d}w}\\). Suppose \\(G=B_R(a)\\), and suppose \\(|f(z)|\leq M\\) on this domain. Then for all \\(r<R\\) we have that
\\[\begin{split}
|f^{(n)}(a)|&=\frac{n!}{2\pi}\left|\int_{\gamma}{\frac{f(w)}{(w-a)^{n+1}}\ \mathrm{d}w}\right|\\\\\
&\leq\frac{n!}{2\pi}\int_{\gamma}{\left|\frac{f(w)}{(w-a)^{n+1}}\right|\ \mathrm{d}w}\\\\\
&\leq\frac{n!}{2\pi}\int_{\gamma}{\frac{M}{r^{n+1}}\ \mathrm{d}w}\\\\\
&=\frac{n!}{2\pi}\cdot\frac{M}{r^{n+1}}\cdot2\pi r\\\\\
&=\frac{n!M}{r^n}.
\end{split}\\]
​Now, we can take the limit \\(r\to R^-\\) to obtain Cauchy's estimate
\\[|f^{(n)}(a)|\leq\frac{n!M}{R^n}.\\]
As we mentioned before, this estimate is quite similar to the one we used to prove the analyticity of harmonic functions. Cauchy's estimate is a powerful statement. Among other things it is used to prove Liouville's theorem, of which the fundamental theorem of algebra is a simple consequence.