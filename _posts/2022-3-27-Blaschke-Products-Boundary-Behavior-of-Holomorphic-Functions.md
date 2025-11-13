---
layout: post
title: "Blaschke Products and Boundary Behavior of Holomorphic Functions"
date: 2022-3-27 12:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

One of the most interesting areas in complex analysis is the study of generalizations of polynomials. One avenue of generalization is the study of entire functions, which behave similarly to polynomials in many ways. Polynomials are also nice because for any choice of \\(n\\) complex numbers, one can easily construct a polynomial with precisely those \\(n\\) numbers as its roots. A natural question is: for some sequence of complex number \\(\\{a_n\\}_{n\in\mathbb{N}}\\), is there an analytic function whose set of roots is precisely \\(\\{a_n\\}\\)?

The answer is yes, as long as the \\(a_n\\) are subject to the mild condition that \\(\\{a_n\\}\_{n\in\mathbb{N}}\\) has no limit points. This condition exists since any analytic function whose set of roots has a limit point must be the constant zero function as is shown by the <a href="https://en.wikipedia.org/wiki/Identity_theorem" target="_blank">identity theorem</a> (this is an idea I used to struggle with; see <a href="http://localhost:4000/bay/2021/06/24/Bump-Functions-and-Divergent-Evolution" target="_blank">here</a>). Traditionally, this result is shown with a long technical argument that hinges on the <a href="https://en.wikipedia.org/wiki/Weierstrass_factorization_theorem" target="_blank">Weierstrass factorization theorem</a>, but if one imposes some more conditions on \\(\\{a_n\\}_{n\in\mathbb{N}}\\), it is much quicker to explicitly construct an analytic function with those roots. This construction is called a <a href="https://en.wikipedia.org/wiki/Blaschke_product" target="_blank">_Blaschke product_</a>.

First, we establish the following lemma that we will need later.

**Lemma:** ​Let \\(0<\|a\|<1\\) and \\(\|z\|\leq r<1\\). Then,
\\[\left|\frac{a+|a|z}{(1-\overline{a}z)a}\right|\leq\frac{1+r}{1-r}.\\]

_Proof_: Put
\\[f(z)=\frac{a+|a|z}{(1-\overline{a}z)a}\\]
\\[g(z)=f(z)-\frac{1}{1-\overline{a}z}=\frac{|a|z}{(1-\overline{a}z)a}.\\]
By the reverse triangle inequality,
\\[|1-\overline{a}z|\geq|1-|\overline{a}z||\geq1-|\overline{a}z|=1-|\overline{a}||z|=1-|a||z|.\\]
Since \\(|a|<1\\) and \\(|z|\leq r\\), the above gives us \\(|1-\overline{a}z|\geq1-r\\). Therefore, \\(\frac{1}{|1-\overline{a}z|}\leq\frac{1}{1-r}\\) and
\\[|g(z)|=\frac{|z|}{|1-\overline{a}z|}\leq\frac{r}{1-r}.\\]
Now by the reverse triangle inequality again,
\\[\left||f(z)|-\frac{1}{|1-\overline{a}z|}\right|\leq\left|f(z)-\frac{1}{1-\overline{a}z}\right|=|g(z)|\leq\frac{r}{1-r}.\\]
Hence,
\\[|f(z)|\leq\frac{1}{|1-\overline{a}z|}+\frac{r}{1-r}\leq\frac{1}{1-r}+\frac{r}{1-r}=\frac{1+r}{1-r}.\\]
\\(\square\\)

Of course, to construct an infinite product, one must know how infinite products work. We will be invoking the following result from the theory of infinite products without proof.

**Theorem:** Let \\(G\\) be a region in \\(\mathbb{C}\\) and let \\(\\{f_n\\}\_{n\in\mathbb{N}}\\) be a sequence in \\(H(G)\\) such that no \\(f_n\\) is identically zero. If \\(\sum_{n=1}^{\infty}{[f_n(z)-1]}\\) converges absolutely and uniformly on compact subsets of \\(G\\) then \\(\prod_{n=1}^{\infty}{f_n(z)}\\) converges in \\(H(G)\\).

This theorem gives us a sufficient condition for an infinite product of holomorphic functions to converge to a holomorphic function. These are the conditions that we will check when we construct our infinite product to confirm that the product is indeed a well-defined holomorphic function.

Let \\(\\{a_n\\}\_{n\in\mathbb{N}}\\) be a sequence of complex numbers with \\(0<\|a_n\|<1\\) for all \\(n\in\mathbb{N}\\) and \\(\sum_{n=1}^{\infty}{(1-\|a_n\|)}<\infty\\). We claim that
\\[B(z)=\prod_{n=1}^{\infty}{\frac{|a_n|}{a_n}\left(\frac{a_n-z}{1-\overline{a_n}z}\right)}\\]
converges in \\(H(B_1(0))\\) with \\(|B(z)|\leq1\\) for all \\(z\in B_1(0)\\). This is what is called a Blaschke product. The roots of \\(B(z)\\) are precisely the prescribed complex numbers \\(\\{a_n\\}_{n\in\mathbb{N}}\\). So if we can establish that this product converges to a holomorphic function, we will have found an analytic function whose roots we have chosen.

Define \\(f_n(z)=\frac{|a_n|}{a_n}\left(\frac{a_n-z}{1-\overline{a_n}z}\right)\\) for each \\(n\in\mathbb{N}\\). We must check that \\(\sum_{n=1}^{\infty}{[f_n(z)-1]}\\) converges absolutely and uniformly on any compact subset of \\(B_1(0)\\). So let \\(K\subseteq B_1(0)\\) be an arbitrary compact subset. We can pick \\(0<r<1\\) so that \\(K\subseteq B_r(0)\\). Now, observe
\\[\begin{split}
f_n(z)-1&=\frac{|a_n|}{a_n}\left(\frac{a_n-z}{1-\overline{a_n}z}\right)-1\\\\\
&=\frac{|a_n|a_n-|a_n|z}{(1-\overline{a_n}z)a_n}-\frac{a_n-|a_n|^2z}{(1-\overline{a_n}z)a_n}\\\\\
&=\frac{|a_n|a_n-a_n+|a_n|^2z-|a_n|z}{(1-\overline{a_n}z)a_n}\\\\\
&=\frac{a_n(|a_n|-1)+|a_n|z(|a_n|-1)}{(1-\overline{a_n}z)a_n}\\\\\
&=(|a_n|-1)\left(\frac{a_n+|a_n|z}{1-\overline{a_n}z}\right).
\end{split}\\]
Since \\(|a_n|<1\\), we have \\(||a_n|-1|=1-|a_n|\\). Moreover, we may recognize the second factor above as the one from the lemma we have proven. Therefore, by the lemma, for all \\(z\in B_r(0)\\),
\\[|f_n(z)-1|\leq(1-|a_n|)\left(\frac{1+r}{1-r}\right).\\]
So for all \\(z\in B_r(0)\\), we have
\\[\sum_{n=1}^{\infty}{|f_n(z)-1|}\leq\frac{1+r}{1-r}\sum_{n=1}^{\infty}{1-|a_n|}<\infty\\]
by assumption. Therefore, \\(\sum_{n=1}^{\infty}{[f_n(z)-1]}\\) converges absolutely on \\(K\\). Uniform convergence follows immediately. Letting \\(M_n=(1-|a_n|)\left(\frac{1+r}{1-r}\right)\\), the above inequality tells us that \\(\sum_{n=1}^{\infty}{M_n}<\infty\\), so \\(\sum_{n=1}^{\infty}{[f_n(z)-1]}\\) converges uniformly on \\(K\\) due to the Weierstrass \\(M\\)-test.

Since none of the of the \\(f_n\\) are identically zero, the theorem we wrote earlier tells us that \\(B(z)\\) converges in \\(H(B_1(0))\\). Of course, the roots are as desired.

\\(|B(z)|\leq1\\) follows as a nice application of the classification of automorphisms of the unit disk (which itself follows from <a href="https://en.wikipedia.org/wiki/Schwarz_lemma" target="_blank">Schwarz's lemma</a>). The classification tells us that every automorphism of the unit disk (i.e. conformal maps from the unit disk to itself) is a Möbius transformation of the form \\(c\varphi_a\\) where \\(|c|=1\\), \\(|a|<1\\), and
\\[\varphi_a(z)=\frac{z-a}{1-\overline{a}z}.\\]
Notice that for every \\(n\in\mathbb{N}\\), we have \\(f_n=\frac{|a_n|}{a_n}\varphi_{a_n}\\). Therefore, each \\(f_n\\) is actually an automorphism of the unit disk, and it follows that their infinite product must also map into the unit disk.

If one does not know the traditional result that if \\(\\{a_n\\}\_{n\in\mathbb{N}}\\) is the zero set of some holomorphic function as long as \\(\\{a_n\\}_{n\in\mathbb{N}}\\) has no limit points, one may still use Blaschke products to answer the following very interesting question. Let \\(G\subseteq\mathbb{C}\\) be an open region and let \\(f\colon G\to\mathbb{C}\\) be a holomorphic function. Is it necessarily true that \\(f\\) extends continuously to the boundary of \\(G\\)? The answer is no, as the following argument with a Blaschke product shows.

For each \\(n\in\mathbb{N}\\), define \\(a\_n=\left(1-\frac{1}{(n+1)^2}\right)\exp{\left(i\sum_{k=1}^{n}{\frac{1}{k}}\right)}\\). By construction, \\(0<\|a_n\|<1\\) for all \\(n\\) and \\(\sum_{n=1}^{\infty}{(1-\|a_n\|)}=\sum_{n=1}^{\infty}{\frac{1}{(n+1)^2}}=\frac{\pi^2}{6}-1<\infty\\). So the Blaschke product with roots \\(\\{a_n\\}_{n\in\mathbb{N}}\\) is well-defined. Let this Blaschke product be \\(f(z)\\).

Since \\(\sum_{k=1}^{\infty}{\frac{1}{k}}=\infty\\) but \\(\frac{1}{k}\to0\\), it is clear that for any angle \\(\theta\\), the argument of \\(a_n\\) will come arbitrarily close to \\(\theta\\) for infinitely many \\(n\\). The details of this are not hard; one may phrase this in terms of the pigeonhole principle. Moreover, \\(1-\frac{1}{(n+1)^2}\to 1\\). So it is clear that every point on the unit circle is a limit point of the sequence \\(\\{a_n\\}\_{n\in\mathbb{N}}\\). That is, every point of \\(\partial B_1(0)\\) is the limit point of the roots of the function \\(f\\) which is holomorphic on \\(B_1(0)\\). Thus, if \\(f\\) is to extend continuously to the boundary of its domain, this extension must be zero on the unit circle \\(\|z\|=1\\) due to continuity. But now the maximum modulus principle implies that \\(f\\) is the constant zero function, a contradiction.

It turns out that there is a pretty developed theory of the space of functions which are holomorphic on the unit disk and can be continuously extended to the boundary (see <a href="https://math.stackexchange.com/questions/6208/isolated-zeros-on-closure-of-a-domain/6210#6210" target="_blank">here</a>). Indeed, the fact that this space is properly contained in the space of bounded holomorphic functions on the disk (which is the <a href="https://en.wikipedia.org/wiki/Hardy_space" target="_blank">_Hardy space_</a> \\(H^{\infty}\\)) demonstrates why many statements of the maximum modulus principle state a hypothesis of the function being holomorphic in some open set \\(G\\) _and_ continuous in the closure \\(\overline{G}\\).