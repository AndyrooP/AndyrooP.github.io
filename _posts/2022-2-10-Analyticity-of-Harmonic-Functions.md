---
layout: post
title: "Analyticity of Harmonic Functions"
date: 2022-2-10 12:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Here is a proof of the analyticity of harmonic functions. This is a bit hard to do from scratch, so I will assume various facts and use notation that is standard (at least in Evans). We denote the volume of the unit ball in \\(\mathbb{R}^n\\) as \\(\alpha(n)\\). The surface measure of the unit sphere in \\(\mathbb{R}^n\\) is then \\(n\alpha(n)\\). We will also denote multi-indices using \\(\alpha\\).

We begin with the assumption that \\(u\\) is harmonic in the open subset \\(U\subseteq\mathbb{R}^n\\). We will employ the following bound on the derivatives of \\(u\\). Let \\(\alpha\\) be a multi-index of order \\(|\alpha|=k\\), and let \\(B_r(x_0)\subseteq U\\). Then,
\\[|D^{\alpha}u(x_0)|\leq\frac{C_k}{r^{n+k}}\\|u\\|_{L^1(B_r(x_0))},\\]
where the constants \\(C_k\\) are given by \\(C_0=\frac{1}{\alpha(n)}\\) and \\(C_k=\frac{(2^{n+1}nk)^k}{\alpha(n)}\\) for \\(k>0\\). This estimate follows from strong induction on \\(k\\) and the mean-value property of harmonic functions.

Fix \\(x_0\in U\\). If we set \\(r=\frac{1}{4}\inf_{x\in\partial U}{|x-x_0|}\\) (which is positive since \\(U\\) is open) and \\(M=\frac{\\|u\\|\_{L^1(B_{2r}(x_0))}}{\alpha(n)r^n}<\infty\\), and apply the above estimate on the derivative, we obtain for any \\(x\in B_r(x_0)\\)
\\[\|D^{\alpha}u(x)\|\leq\frac{(2^{n+1}n\|\alpha\|)^{\|\alpha\|}}{r^{n+\|\alpha\|}\alpha(n)}\\|u\\|\_{L^1(B_r(x))}=\left[\frac{\\|u\\|\_{L^1(B_r(x))}}{\alpha(n)r^n}\right]\left(\frac{2^{n+1}n\|\alpha\|}{r^n}\right)^{\|\alpha\|}.\\]
By the triangle inequality, \\(B_r(x)\subseteq B_{2r}(x_0)\\), so we can modify the bracketed factor on the right hand side of the above inequality to \\(M\\). This gives us
\\[\|D^{\alpha}u(x)\|\leq M\left(\frac{2^{n+1}n}{r}\right)^{|\alpha|}|\alpha|^{|\alpha|}.\\]
Now, for every \\(k\in\mathbb{N}\\), notice that \\(\frac{k^k}{k!}\\) is merely one term in the Taylor expansion of \\(e^k\\), so \\(k^k<e^k\\). It follows that \\(|\alpha|^{|\alpha|}<e^{|\alpha|}\\). Moreover, the multinomial theorem states that \\((x_1+\dots+x_n)^k=\sum_{|\alpha|=k}{\binom{|\alpha|}{\alpha}x^{\alpha}}\\), where \\(x^{\alpha}=\prod_{j=1}^{n}{x_j^{\alpha_j}}\\) and \\(\binom{|\alpha|}{\alpha}=\frac{|\alpha|!}{\alpha!}=\frac{|\alpha|!}{\prod_{j=1}^{n}{\alpha_j!}}\\). It follows that \\(n^k=(1+\dots+1)^k=\sum_{|\alpha|=k}{\frac{|\alpha|!}{\alpha!}}\\). So for any fixed \\(\alpha\\), \\(\frac{|\alpha|!}{\alpha!}\\) is a single term in the expansion of \\(n^{|\alpha|}\\), and thus \\(\frac{|\alpha|!}{\alpha!}\leq n^{|\alpha|}\\) or \\(|\alpha!|\leq n^{|\alpha|}\alpha!\\). Combining all of these estimates, we have
\\[\\|D^{\alpha}u\\|\_{L^{\infty}(B_r(x_0))}\leq\sup_{x\in B\_r(x\_0)}{\|D^{\alpha}u(x)\|}\leq M\left(\frac{2^{n+1}n}{r}\right)^{\|\alpha\|}\|\alpha\|^{\|\alpha\|}<M\left(\frac{2^{n+1}ne}{r}\right)^{\|\alpha\|}.\\]
Since \\(1\leq|\alpha|!\leq n^{|\alpha|}\alpha!\\), so \\(\left(\frac{2^{n+1}ne}{r}\right)^{|\alpha|}\leq\left(\frac{2^{n+1}n^2e}{r}\right)^{|\alpha|}\alpha!\\) and we obtain the estimate
\\[\\|D^{\alpha}u\\|\_{L^{\infty}(B_r(x_0))}<M\left(\frac{2^{n+1}n^2e}{r}\right)^{|\alpha|}\alpha!\\]
The Taylor expansion of \\(u\\) about \\(x_0\\) is given by
\\[\sum_{\alpha}{\frac{D^{\alpha}u(x_0)}{\alpha!}(x-x_0)^{\alpha}}.\\]
​We wish to show that this power series converges in some neighborhood. To do this, we study the remainder term,
\\[R_N(x)=u(x)-\sum_{k=0}^{N-1}{\sum_{|\alpha|=k}{\frac{D^{\alpha}u(x_0)}{\alpha!}(x-x_0)^{\alpha}}}.\\]
Consider the function \\(g\colon\mathbb{R}\to\mathbb{R}\\) given by \\(g(t)=u(x_0+t(x-x_0))\\). By applying the mean-value remainder form of Taylor's theorem to the Taylor expansion of \\(g\\) about \\(0\\) evaluated at \\(t=1\\), we obtain
\\[R_N(x)=g(1)-\sum_{k=0}^{N-1}{\sum_{|\alpha|=k}{\frac{D^{\alpha}u(x_0)}{\alpha!}(x-x_0)^{\alpha}}}=\sum_{|\alpha|=N}{\frac{D^{\alpha}u(x_0+\lambda(x-x_0))}{\alpha!}(x-x_0)^{\alpha}}\\]
for some \\(\lambda\in[0,1]\\).

Now, suppose that we are considering \\(x\\) such that \\(|x-x_0|<\frac{r}{2^{n+2}n^3e}\\). In particular, we will have \\(x\in B_r(x_0)\\), so by the convexity of the ball, \\(x_0+\lambda(x-x_0)\in B_r(x_0)\\) and we will have access to our estimate of the \\(L^{\infty}\\) norm of \\(D^{\alpha}u\\). Combining all of the bounds, we obtain
\\[|R_n(x)|\leq M\sum_{|\alpha|=N}{\left(\frac{2^{n+1}n^2e}{r}\right)^N\left(\frac{r}{2^{n+2}n^3e}\right)^N}=M\sum_{|\alpha|=N}{\frac{1}{(2n)^N}}.\\]
The relevant multi-indices with order \\(N\\) that we are summing over are \\(N\\)-tuples of integers from the set \\(\\{1,2,\dots,n\\}\\), because it is these integers that correspond to the components that can exist in \\(\mathbb{R}^n\\). Hence, there are \\(n^N\\) multi-indices we are summing over, so
​\\[M\sum_{|\alpha|=N}{\frac{1}{(2n)^N}}=\frac{Mn^N}{(2n)^N}=\frac{M}{2^N}.\\]
Thus, the remainder vanishes as we take \\(N\to\infty\\) and the Taylor series converges in the neighborhood we have defined.