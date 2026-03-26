---
layout: post
title: "Some Theory of Curves"
date: 2026-03-26 16:00:00 -0400
blurb: "The Fermat curve of degree $n>2$ does not admit a dominant rational map from the projective line. This can be shown in a low-brow way or with more powerful invariants."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

In this post, we discuss the following theorem.

**Theorem 1:** If $n>2$ is an integer, there is no dominant rational map from $\mathbb{P}\_{\mathbb{C}}^1$ to the curve cut out by $x^n+y^n=z^n$ in $\mathbb{P}\_{\mathbb{C}}^2$.

The curve cut out by $x^n+y^n=z^n$ in $\mathbb{P}_{\mathbb{C}}^2$ is called the <a href="https://en.wikipedia.org/wiki/Fermat_curve" target="_blank">*Fermat curve*</a>, and we will often denote it by $F\_{\mathbb{C}}^n$. More generally, we will use the notation $F\_{k}^n$ if we are working over the base field $k$.

We will discuss two different ways to prove this. The first is a lowbrow method, relying on some explicit manipulation of polynomials. We will then see that this result follows more abstractly from invariants of curves.

## Lowbrow Proof

This is a proof by infinite descent that uses some clever algebra to generate polynomial solutions to Fermat's equation of strictly smaller degree, given some starting solutions.

*Proof of Theorem 1:* Suppose there exists a dominant rational map $\varphi\colon\mathbb{P}\_{\mathbb{C}}^1\dashrightarrow F\_{\mathbb{C}}^n$ from the projective line to the Fermat curve, where $n>2$. After dehomogeneization in an affine chart, this rational map should be given by the data of three rational functions $f(t)$, $g(t)$, and $h(t)$, satisfying the equation $f(t)^n+g(t)^n=h(t)^n$. By Theorem II.6.8 of Hartshorne, since the projective line is a complete curve, it follows that the image of $\varphi$ is either a point or $F_{\mathbb{C}}^n$ itself. Since this map is dominant, we note that the image of $\varphi$ cannot be a single point. That is, the rational functions $f(t)$, $g(t)$, and $h(t)$ should not be constants. Clearing denominators and canceling common factors, we obtain polynomials $F(t)$, $G(t)$, and $H(t)$ that are relatively prime and satisfy $F(t)^n+G(t)^n=H(t)^n$. 

Suppose furthermore that the polynomials $F$, $G$, and $H$ solving Fermat's equation are chosen so that $\min{(\deg{F},\deg{G})}$ is minimal amongst all tuples of polynomial solutions to Fermat's equation. Without loss of generality, let us assume that $\deg{F}=\min{(\deg{F},\deg{G})}$. Note that

$$F(t)^n=H(t)^n-G(t)^n=\prod_{j=1}^{n}{\left(H(t)-\zeta^jG(t)\right)},$$

where $\zeta$ is a primitive $n$<sup>th</sup> root of unity. We claim that each factor $H(t)-\zeta^jG(t)$ is itself an $n$<sup>th</sup> power. Indeed, note that if $H(t)-\zeta^jG(t)$ and $H(t)-\zeta^kG(t)$ share a common factor for $j\neq k$ (with $1\leq j,k\leq n$), they must also share a common root. Evaluation of both factors at that root then forces either $H$ and $G$ to share a common factor, or $\zeta^j=\zeta^k$, a contradiction in either case. Hence, each factor in our factorization above has distinct factors. Since the product above is itself an $n$<sup>th</sup> power, namely $F(t)^n$, and $\mathbb{C}[t]$ is a UFD, it must be the case that each factor must be an $n$<sup>th</sup> power as claimed.

Now consider the system of equations

$$\begin{cases}
1+\alpha=\beta,\\
1+\zeta\alpha=\zeta^2\beta.
\end{cases}$$

The solution to this system of equations is given by $\alpha = -\frac{\zeta + 1}{\zeta}$ and $\beta = -\frac{1}{\zeta}$. By construction, we have that

$$\left[H(t)-G(t)\right]+\alpha\left[H(t)-\zeta G(t)\right]=\beta\left[H(t)-\zeta^2G(t)\right].$$

We have already shown that each factor in the brackets is itself an $n$<sup>th</sup> power. Therefore, we may define the polynomials $\tilde{F}(t)=\left[H(t)-G(t)\right]^{1/n}$, $\tilde{G}(t)=\alpha^{1/n}\left[H(t)-\zeta G(t)\right]^{1/n}$, and $\tilde{H}(t)=\beta^{1/n}\left[H(t)-\zeta^2 G(t)\right]^{1/n}$, and they will satisfy $\tilde{F}(t)^n+\tilde{G}(t)^n=\tilde{H}(t)^n$. Since $n>2$, we have that $\alpha$ and $\beta$ are both nonzero, so all three of these new polynomials are nonconstant. But by construction, the degrees of $\tilde{F}$ and $\tilde{G}$ are both strictly less than the degree of $F$, contradicting the minimality of $\min{(\deg{F},\deg{G})}$. $\square$

Notice that the proof above fails for $n=2$ because that would force $\alpha=0$ and so $\tilde{G}=0$.

The heart of what we have shown is that no polynomials satisfy Fermat's equation $F(t)^n+G(t)^n=H(t)^n$ for $n>3$. This is sometimes called <a href="https://abblock.github.io/old_math_notes/Fermat_and_Polynomials.pdf" target="_blank">*Fermat's last theorem for polynomials*</a>. The linked file offers three approaches to this. The first one is essentially what we have shown above. We will expand more on the third approach which is more abstract and geometric in nature. Our proof above heavily relies on the complex numbers, but much of the geometric approach will work more generally over any base field.

## Highbrow Proof

The main piece of technology we need to discuss is the Riemann--Hurwitz theorem. But before we do this, let us discuss in more detail how dominant rational maps of the kind we are interested in actually promote to genuine morphisms. The main result is the following.

**Theorem 15.3.1, Curve-to-Projective Extension, (Vakil):** Suppose $C$ is a pure dimension $1$ Noetherian scheme over an affine base $S=\operatorname{Spec}{A}$, and $p\in C$ is a regular closed point of it. Suppose $Y$ is a projective $S$-scheme. Then any morphism $C\setminus\\{p\\}\to Y$ of $S$-schemes extends to all of $C$.

Applying this theorem inductively, we can see that under the same hypotheses, a morphism from the complement of any finite set of regular closed points will extend to all of $C.$

The projective line is certainly a pure dimension $1$ Noetherian scheme. The Fermat curve over a field $k$ is a projective $k$-scheme (see Definition 4.5.10 of Vakil). A rational map $\mathbb{P}\_k^1\dashrightarrow F\_{k}^n$, for any $n$ can be represented by a genuine morphism defined on some open subset $U\subseteq\mathbb{P}\_k^1$. But the Zariski topology on $\mathbb{P}^1$ is quite simple and such a subset is simply the complement of some finite collection of closed points (and all closed points of projective space are regular). By the theorem above, this representative will then extend uniquely to a morphism defined on all of $\mathbb{P}_k^1$. Therefore, the existence of a dominant rational map $\mathbb{P}\_k^1\dashrightarrow F\_{k}^n$ is really just equivalent to the existence of a surjective morphism $\mathbb{P}\_k^1\to F\_{k}^n$. This is important for us since Riemann--Hurwitz does not directly apply to rational maps between curves, but instead works for certain kinds of morphisms.

Now we need to understand something about the topology of the curves involved in our question. A basic topological property of the projective spaces is that they are irreducible. We can also show that over most fields, the same is true of the Fermat curve for any $n$.

**Lemma 1:** Let $n$ be a positive integer and let $k$ be a field whose characteristic does not divide $n$. The Fermat curve $F_k^n$ is irreducible.

*Proof:* We need to show that $x^n+y^n-z^n$ is irreducible in $k[x,y,z]$. 

Note that the polynomial $T^n-1\in k[T]$ has formal derivative $nT^{n-1}$. Since the characteristic of $k$ does not divide $n$, this formal derivative is not the zero polynomial, and so it does not share any roots with $T^n-1$ in the algebraic closure $\overline{k}$ of $k$. Hence there are $n$ distinct $n$<sup>th</sup> roots of unity in $\overline{k}$. Note that the factorization

$$y^n-z^n=\prod_{\zeta^n=1}{y-\zeta z},$$

where product ranges over all $n$<sup>th</sup> roots of unity in $\overline{k}$ counted with multiplicity, holds purely formally by Vieta's formulas. Since there are $n$ distinct $n$<sup>th</sup> roots of unity, it follows that this factorization consists of $n$ distinct linear factors, and so this is the irreducible factorization of $y^n-z^n$ in $\overline{k}[y,z]$.

In particular, if we fix a root of unity $\zeta$, then $y-\zeta z$ is an irreducible factor of $y^n-z^n$ in the ring $\overline{k}[y,z][x]$ whose square does not divide $y^n-z^n$. Since $\overline{k}[y,z][x]$ is a UFD, it follows that $\langle y-\zeta z\rangle$ is a prime ideal, and $y^n-z^n\notin\langle y-\zeta z\rangle^2$. Of course, $1\notin \langle y-\zeta z\rangle$ and $y^n-z^n\in \langle y-\zeta z\rangle$, so $x^n+y^n-z^n$ is irreducible in $\overline{k}[y,z][x]\cong\overline{k}[x,y,z]$ by the <a href="https://en.wikipedia.org/wiki/Eisenstein%27s_criterion#Generalized_criterion" target="_blank">generalized Eisenstein's criterion</a>. Hence, it is irreducible over $k[x,y,z]$. $\square$

Of course, working in the algebraic closure of $k$ in the proof above is overkill---it suffices to work in the splitting field of $T^n-1$. Also note that the condition that the characteristic of $k$ does not divide $n$ is essential. Suppose that $p=\operatorname{char}{k}$. Since the <a href="https://en.wikipedia.org/wiki/Freshman%27s_dream#Prime_characteristic" target="_blank">freshman's dream</a> is valid in prime characteristic, if $p\mid n$ we would have the factorization $x^n+y^n-z^n=(x^{n/p}+y^{n/p}-z^{n/p})^p$.

The topological data that breaks the problem open is the *genus* of the curves.

**Definition 1:** Let $X$ be a nonsingular variety and let $\omega_X$ be its canonical bundle. The **geometric genus of $X$** is defined to be the zeroth Betti number of $\omega_X$, denoted $g(X):=h^0(X,\omega_X)$.

Since the zeroth sheaf cohomology is just the space of global sections, we can also think of the geometric genus as the dimension of the space of global sections of the canonical bundle. We first show how to compute the geometric genus of $\mathbb{P}^1_k$ by finding its canonical bundle in two different ways.

**Theorem 2:** $g(\mathbb{P}^1_k)=0$.

*Proof 1 of Theorem 2:* Consider the standard affine charts $U_0=\operatorname{Spec}{k[x_{1/0}]}$ and $U_1=\operatorname{Spec}{k[x_{0/1}]}$ of the projective line, with the change of coordinates given by $x_{1/0}=\frac{1}{x_{0/1}}$. The affine line has cotangent bundle $\Omega_{k[x]/k}\cong\mathcal{O}\_{\mathbb{A}^1\_k}$, which is a line bundle. Therefore, the cotangent bundle $\Omega\_{\mathbb{P}^1\_k/k}$ must be a line bundle. That is, we must have $\omega_X=\Omega\_{\mathbb{P}^1\_k/k}\cong\mathcal{O}\_{\mathbb{P}\_k^1}(m)$ for some integer $m$.

Consider the section $dx\_{1/0}$ of the cotangent bundle over $U_0$. Since $x\_{1/0}=\frac{1}{x\_{0/1}}$, we have the relation $dx\_{1/0}=-\frac{1}{x\_{0/1}^2}\, dx\_{0/1}$, hence this section has a pole of order $2$ in $U_0$ wherever $x\_{0/1}=0$. It follows that $\Omega\_{\mathbb{P}^1\_k/k}\cong\mathcal{O}\_{\mathbb{P}\_k^1}(-2)$. This sheaf has no nonzero global sections, hence $g(\mathbb{P}^1_k)=0$ as claimed. $\square$

We can also calculate the genus of the projective line without getting our hands dirty by using the Euler sequence.

*Proof 2 of Theorem 2:* We first write the Euler sequence:

$$0\longrightarrow\Omega_{\mathbb{P}^1_k/k}\longrightarrow\mathcal{O}_{\mathbb{P}^1_k}(-1)\oplus \mathcal{O}_{\mathbb{P}^1_k}(-1)\longrightarrow \mathcal{O}_{\mathbb{P}^1_k} \longrightarrow0.$$

Now we take determinants in this short exact sequence (using Exercise 7.29 of Görtz--Wedhorn or Exercise 5.16(d) of Hartshorne). This yields

$$\det{\Omega_{\mathbb{P}^1_k/k}}\otimes\det{\mathcal{O}_{\mathbb{P}^1_k}}\cong\det{[\mathcal{O}_{\mathbb{P}^1_k}(-1)\oplus \mathcal{O}_{\mathbb{P}^1_k}(-1)]}.$$

We have $\omega\_{\mathbb{P}^1\_k}=\det{\Omega_{\mathbb{P}^1\_k/k}}$ and $\det{\mathcal{O}\_{\mathbb{P}^1\_k}}\cong \mathcal{O}\_{\mathbb{P}^1\_k}$. Hence, the above becomes

$$\omega_{\mathbb{P}^1_k}\cong \det{[\mathcal{O}_{\mathbb{P}^1_k}(-1)\oplus \mathcal{O}_{\mathbb{P}^1_k}(-1)]}\cong \det{\mathcal{O}_{\mathbb{P}^1_k}(-1)}\otimes\det{\mathcal{O}_{\mathbb{P}^1_k}(-1)}\cong\mathcal{O}_{\mathbb{P}^1_k}(-1)\otimes\mathcal{O}_{\mathbb{P}^1_k}(-1)\cong\mathcal{O}_{\mathbb{P}^1_k}(-2).$$

So just as before, we have $g(\mathbb{P}^1_k)=0$ as claimed. $\square$

### Arithmetic Genus

Calculating the geometric genus of the Fermat curve will be harder. To do this, we will instead calculate a different invariant, the *arithmetic genus*, and then see that in the smooth case the two invariants should match.

**Definition 2:** Let $X$ be a scheme of dimension $n$. The **arithmetic genus of $X$** is defined to be $p_a(X):=(-1)^n(\chi(X,\mathcal{O}_X)-1)$.

It turns out the arithmetic genus looks a lot simpler in the case of an integral projective curve over an algebraically closed field (such as a compact Riemann surface). To show this, we first need the following lemma which is an algebraic generalization of <a href="https://en.wikipedia.org/wiki/Liouville%27s_theorem_(complex_analysis)#On_compact_Riemann_surfaces" target="_blank">Liouville's theorem</a>.

**Lemma 2:** Let $k$ be an algebraically closed field and let $X$ be a connected, reduced, proper $k$-scheme. Then the only global functions on $X$ are the constant functions: $\Gamma(X,\mathcal{O}_X)=k$.

*Proof:* This argument is given by 11.4.7 in Vakil. Let $f\in\Gamma(X,\mathcal{O}_X)$ be a global function on $X$. Recall that morphisms $X\to\mathbb{A}\_k^1$ are in correspondence with ring homomorphisms $k[t]\to\Gamma(X,\mathcal{O}_X)$, which by evaluation at $t$ are in "$\sharp$-correspondence" with global functions in $\Gamma(X,\mathcal{O}_X)$ (see 7.6.1 of Vakil). Let $\pi\colon X\to\mathbb{A}\_k^1$ be the morphism corresponding to $f$ under this correspondence. Let $\iota\colon\mathbb{A}\_k^1\hookrightarrow\mathbb{P}\_k^1$ be the standard open embedding.

We know that $\mathbb{P}\_k^1$ is separated over $k$ (Vakil 11.2.8) and $X$ is proper over $k$ by assumption, hence by Proposition 11.4.4(e) of Vakil/Corollary II.4.8 of Hartshorne, it follows that the composition $\iota\circ\pi$ is proper. In particular, the composition is closed. Since $X$ is connected, it follows that the image of $\iota\circ\pi$ is a closed, connected subset of $\mathbb{P}_k^1$, so the image is either a single closed point or all of $\mathbb{P}_k^1$. But the embedding $\iota$ is not surjective, so the image of $\iota\circ\pi$ must be a single closed point. In particular, this must be a closed point of $\mathbb{A}_k^1$, and such a point can be identified with an element $p\in k$ since $k$ is algebraically closed.

Since $X$ is reduced and the point $p$ is closed, Corollary 9.4.5 and Exercise 9.4.A of Vakil imply that the scheme-theoretic image of $\pi$ is exactly $p$ with the reduced structure. This means $\pi$ factors as the composition of the structure morphism $X\to\operatorname{Spec}{k}$ and the closed embedding $\operatorname{Spec}{k}\hookrightarrow\mathbb{A}_k^1$ which identifies $\operatorname{Spec}{k}$ with the closed point $p$. By the functoriality of the $\sharp$-correspondence, it follows that $\pi$ corresponds exactly to the global section $f\in\Gamma(X,\mathcal{O}_X)$ which is equal to the constant map $k[t]\to k$ sending $t\mapsto p$, composed with the ring homomorphism $k\to\Gamma(X,\mathcal{O}_X)$ induced by the structure morphism of $X$. $\square$

The upshot of Lemma 2 is that if $X$ is an integral projective curve over an algebraically closed field (like a compact Riemann surface), then $h^0(X,\mathcal{O}_X)=1$. Then the arithmetic genus of $X$ simplifies to the first Betti number: $p_a(X)=h^1(X,\mathcal{O}_X)$. Let us specialize even further to the case that $X$ is a connected, compact Riemann surface. Let us further assume the <a href="https://en.wikipedia.org/wiki/Algebraic_geometry_and_analytic_geometry#GAGA" target="_blank">GAGA miracle</a> that the Betti numbers of the sheaf of algebraic functions on $X$ match the Betti numbers of the sheaf of holomorphic functions on $X$. Then due to the <a href="https://anpaul.onrender.com/2025/12/11/Hodge-decomposition-for-curves" target="_blank">Hodge decomposition on the cohomology of $X$</a>, we have that the topological Euler characteristic is

$$\chi(X,\underline{\mathbb{C}})=1-2h^1(X,\mathcal{O}_X)+1=2-2p_a(X).$$

But recall that the topological Euler characteristic equals $2-2g$ for closed orientable surfaces, where $g$ is the topological genus. Hence the arithmetic genus is equal to the topological genus of $X$! So it is not entirely unfair to consider the quantity $p_a(X)$ a type of "genus". Let us push further and argue that in the case we are interested in, the arithmetic genus will agree with the geometric genus.

**Theorem 3:** Let $X$ be a smooth irreducible projective curve. Then $g(X)=p_a(X)$.

*Proof:* This follows immediately from Serre duality:

$$g(X)=h^0(X,\omega_X)=h^0(X,\omega_X\otimes(\mathcal{O}_X)^{*})=h^1(X,\mathcal{O}_X)=p_a(X)$$

$\square$

Hence in the case of a connected, compact Riemann surface, the topological genus equals the arithmetic genus, which equals the geometric genus. This gives another justification for Theorem 2 in the case that $k=\mathbb{C}$, since the projective line $\mathbb{C}P^1$ is topologically the sphere $S^2$ which has genus $0$. More generally, orientable compact connected surfaces are classified to be the connected sums of tori with the sphere as shown below.

<div style="text-align: center;">
<img src="/myassets/images/Theory-of-curves/genus.png" alt="diagram" width="700px">
</div>

So when one computes a fairly abstract invariant, namely arithmetic genus, of a compact, connected complex curve, one is really just identifying which of the surfaces, depicted in the (infinitely long) list above, the complex curve looks like. Now we work toward actually computing the arithmetic genus.

#### The Hilbert Polynomial

The main point of this section is to define a polynomial invariant of coherent sheaves on projective $k$-schemes. This polynomial will be closely related to the arithmetic genus of the scheme and will allow us to compute the arithmetic genus of degree $d$ curves in the projective plane $\mathbb{P}_k^2$. We closely follow the construction/proof described in Theorem 18.6.1 of Vakil. First, we need to establish a theorem.

**Lemma 3:** Let $k$ be an infinite field. For any finite set of points $S\subseteq\mathbb{P}_k^n$, there exists a hyperplane that does not intersect $S$.

*Proof:* Let $S=\\{p_1,\dots,p_m\\}$. We will induct on $m$. Write $p_i=[p_i^0,p_i^1,\dots,p_i^n]$ for each $i$. Note that for each $i$, there exists at least one $j$ for which $p_i^j\neq0$. The case of $m=1$ is easy: pick $j$ for which $a_1^j\neq0$, and then the hyperplane cut out by $x_j$ does not contain $p_1$.

Now suppose that the hyperplane cut out by $\sum_{\ell=0}^{n}{a_{\ell}x_{\ell}}=0$ does not intersect $S$ and let $p_{m+1}$ be a point distinct from all points in $S$. Let $j$ be chosen so that $p_{m+1}^j\neq0$ and define $T=\\{1\leq i\leq m+1\colon p_i^j\neq0\\}$. Now observe that since $k$ is infinite and $T$ is finite, we may choose a $\lambda\in k$ such that 

$$\lambda\neq-\left(p_i^j\right)^{-1}\sum_{\substack{0\leq \ell\leq n \\\\\ \ell\neq j}}{a_{\ell}p_i^{\ell}}$$

for any $i\in T$. Then by construction, the hyperplane cut out by

$$(a_j+\lambda)x_j+\sum_{\substack{0\leq \ell\leq n \\\\\ \ell\neq j}}{a_{\ell}x_{\ell}}$$

avoids $\\{p_1,p_2,\dots,p_{m+1}\\}$. This completes the induction. $\square$

 **Theorem 4:** Let $k$ be an infinite field and let $X$ be a projective $k$-scheme. Suppose $\mathcal{F}$ is a coherent sheaf on $X$ and $\mathcal{L}$ is a very ample invertible sheaf on $X$. Then there exists an effective Cartier divisor $D$ on $X$, that does not contain the associated points, with $\mathcal{L}\cong\mathcal{O}(D)$.

*Proof:* Since $\mathcal{L}$ is very ample, there exist global sections $s_0,s_1,\dots,s_n$ of $\mathcal{L}$, with no common zeros, inducing a closed embedding $\pi\colon X\hookrightarrow\mathbb{P}_k^n$. Finitely generated modules over Noetherian rings have finitely many associated prime ideals (Vakil 6.6.17), so the coherent sheaf $\mathcal{F}$ has finitely many associated points. By Lemma 3 above, we can find a hyperplane $H\subseteq\mathbb{P}_k^n$ that avoids the image under $\pi$ of these points.

Note that by construction, $\mathcal{L}\cong\pi^{\*}(\mathcal{O}\_{\mathbb{P}\_k^n}(1))$. So if $h$ is the section of $\mathcal{O}_{\mathbb{P}\_k^n}(1)$ cutting out the hyperplane $H$, the pullback $\pi^{\*}(h)$ can be identified with a global section $s$ of $\mathcal{L}$. The vanishing locus of this section avoids all of the associated points of $P$ since $H$ avoids the image of the associated points. Therefore, by Exercise 15.6.D of Vakil, the vanishing locus of $s$ cuts out an effective Cartier divisor $D$, and $\mathcal{L}\cong\mathcal{O}(D)$. $\square$

Now we can state the main definition of this section, though to check that the definition is well-formed, we will need to use Theorem 4 above.

**Definition 3/Theorem 5:** Let $\mathcal{F}$ be a coherent sheaf on a projective $k$-scheme $X\hookrightarrow\mathbb{P}_k^n$. The Euler characteristic $\chi(X,\mathcal{F}(m))$ is polynomial in $m$, and the degree of this polynomial is $\dim{\operatorname{Supp}{\mathcal{F}}}$. This polynomial is called the **Hilbert polynomial of $\mathcal{F}$**.

*Proof:* First, consider the case that $\mathcal{F}$ is the zero sheaf: all of the Betti numbers of the twists are zero, so the Euler characteristic is the constant zero polynomial. Now we specialize to the case that $\mathcal{F}$ is not the zero sheaf.

We induct on $\dim{\operatorname{Supp}{\mathcal{F}}}$. Note that cohomology respects base change (Exercise 18.2.H of Vakil) so we may assume without loss of generality that $k$ is an infinite field. Now we may take $\mathcal{L}=\mathcal{O}_X(1)$ in Theorem 4 above. The theorem then tells us that there exists a hyperplane $D$ that is the vanishing of the global section $s\in\Gamma(X,\mathcal{O}_X(1))$. Moreover, $D$ avoids all of the associated points of $\mathcal{F}$.

First if $\dim{\operatorname{Supp}{\mathcal{F}}}=0$, the support of $\mathcal{F}$ must be some finite set of closed points $x_1,x_2,\dots,x_{\ell}$ (see Vakil Exercise 12.1.C). Therefore, $\mathcal{F}$ is a finite direct sum of skyscraper sheaves, with each summand supported at exactly one of the $x_i$. Note that skyscraper sheaves are flabby since we may extend every section to a global section by just choosing a fixed value in the support and zero elsewhere. Therefore, the higher cohomology of skyscraper sheaves vanish, so the only nontrivial Betti number is $h^0$. Since cohomology commutes with colimits, it follows that the same is true of $\mathcal{F}$. Twisting does not change the stalks, so we conclude that $\chi(X,\mathcal{F}(m))=h^0(X,\mathcal{F})$, which is a constant polynomial in $m$.

Now suppose that $\mathcal{F}$ is a nonzero sheaf and coherent sheaves with lower dimensional supports than $\mathcal{F}$ have Hilbert polynomials. Note that $\mathcal{F}$ and $\mathcal{F}(-1)$ are both $\mathcal{O}_X$-modules. Moreover, they are both locally free sheaves of the same rank, so they have isomorphic stalks. Their stalks $\mathcal{F}\_x\cong\mathcal{F}(-1)\_x$ are $\mathcal{O}\_{X,x}$-modules, and we have constructed $s$ in such a way that $s$ does not vanish at any associated point of $M$. Therefore by Proposition 6.6.13 of Vakil, the germ of $s$ is not a zero divisor for $\mathcal{F}\_x\cong\mathcal{F}(-1)\_x$ at any point $x\in X$. Hence the morphism $\mu_s\colon\mathcal{F}(-1)\to\mathcal{F}$ induced by multiplication by $s$ is a monomorphism of sheaves and we have a short exact sequence

$$0\longrightarrow\mathcal{F}(-1)\xrightarrow[]{\,\, \mu_s\,\,}\mathcal{F}\longrightarrow\operatorname{coker}{\mu_s}\longrightarrow0.$$

Note that $\operatorname{coker}{\mu_s}$ is a coherent sheaf (since the category of coherent sheaves is Abelian). Now it follows from a fact in commutative algebra (Vakil Exercise 6.6.D) that $\operatorname{Supp}{\operatorname{coker}{\mu_s}}=(\operatorname{Supp}{\mathcal{F}})\cap D$. By Exercise 12.3.D(a) of Vakil, $V(x)$ meets every irreducible component of $\operatorname{Supp}{\mathcal{F}}$ of positive dimension. In particular, it meets an irreducible component of maximal dimension. Since $\mathcal{F}$ is nonzero, by Krull's principal ideal theorem, the codimension of the intersection of $V(x)$ in every irreducible component of $\operatorname{Supp}{\mathcal{F}}$ is equal to $1$. Since this is true in particular in an irreducible component of $\operatorname{Supp}{\mathcal{F}}$ of maximal dimension, it follows that $\dim{\operatorname{Supp}{\operatorname{coker}{\mu_s}}}=\dim{\operatorname{Supp}{\mathcal{F}}}-1$.

$\mathcal{O}_X(m)$ is a locally free sheaf, so tensoring with it will preserve exactness. Hence for any $m$, we may twist the short exact sequence above to obtain

$$0\longrightarrow\mathcal{F}(m-1)\longrightarrow\mathcal{F}(m)\longrightarrow(\operatorname{coker}{\mu_s})(m)\longrightarrow0.$$

Euler characteristic is additive on exact sequences so for all $m$, we have

$$\chi(X,\mathcal{F}(m))-\chi(X,\mathcal{F}(m-1))=\chi(X,(\operatorname{coker}{\mu_s})(m)).$$

By the inductive hypothesis, the right hand side of the above equation is a polynomial in $m$ of degree $\dim{\operatorname{Supp}{\operatorname{coker}{\mu_s}}}=\dim{\operatorname{Supp}{\mathcal{F}}}-1$. Now it is a combinatorial exercise in finite differences that the above identity implies that $\chi(X,\mathcal{F}(m))$ is a polynomial in $m$ of degree $\dim{\operatorname{Supp}{\mathcal{F}}}$. This completes the induction. $\square$

For $\mathcal{F}=\mathcal{O}_X$, this polynomial is often called the *Hilbert polynomial of $X$*, which we will denote by $p_X(m)$. Observe that by definition, the constant term of the Hilbert polynomial is closely related to the arithmetic genus: $p_X(0)=1+(-1)^np_a(X)$. Note that by the <a href="https://en.wikipedia.org/wiki/Coherent_sheaf_cohomology#Vanishing_theorems" target="_blank">Serre vanishing theorem</a>, we have $\chi(X,\mathcal{F}(m))=h^0(X,\mathcal{F}(m))$ for $m$ sufficiently large. 

These facts give us the historical point of view. The Hilbert polynomial was first obtained by calculating the number of independent degree $m$ functions on $X$, which is the Betti number $h^0(X,\mathcal{O}_X(m))$. The observation was that for large $m$ these numbers fit a polynomial, and that when $X$ is a curve the constant term of this polynomial was effectively the topological genus of the curve! This is probably the closest thing to magic one can experience with just paper and pen.

We now calculate the Hilbert polynomial in some nice cases. Note that for $m\geq0$, $h^0(\mathbb{P}_k^n,\mathcal{O}(m))$ counts the number of degree $m$ monomials in $n$ variables. Hence by Serre vanishing, we have

$$p_{\mathbb{P}_k^n}(m)=\binom{m+n}{n}.$$

In particular, $p_a(\mathbb{P}_k^n)=(-1)^n\left(\binom{n}{n}-1\right)=0$, which is very reasonable! Now we can calculate the Hilbert polynomial which will give us the genus of the Fermat curve.

**Theorem 6:** The Hilbert polynomial of a degree $d$ hypersurface $H$ in $\mathbb{P}_k^n$ is

$$p_H(m)=\binom{m+n}{n}-\binom{m+n-d}{n}.$$

*Proof:* Let $\iota\colon H\hookrightarrow\mathbb{P}_k^n$ be the closed embedding. If $H$ is cut out by the degree $d$ function $f\in\mathcal{O}\_{\mathbb{P}\_k^n}(d)$, multiplication by $f$ induces the short exact sequence for the closed embedding:

$$0\longrightarrow\mathcal{O}_{\mathbb{P}_k^n}(-d)\xrightarrow[]{\,\, \mu_f\,\,}\mathcal{O}_{\mathbb{P}_k^n}\longrightarrow\iota_*(\mathcal{O}_H)\longrightarrow0.$$

Hence by the additivity of Euler characteristic, it follows that

$$p_H(m)=p_{\mathbb{P}_k^n}(m)-p_{\mathbb{P}_k^n}(m-d)=\binom{m+n}{n}-\binom{m+n-d}{n}.$$

$\square$

**Corollary:** The arithmetic genus of a degree $n$ curve in the projective plane is

$$\frac{(n-1)(n-2)}{2}.$$

Hence by Theorem 3, the geometric genus of the Fermat curve $F_k^n$ is as above as well.

### The Riemann--Roch Theorem

We have been making extensive use of cohomological techniques so far, and we will continue with another result about divisors on curves, namely the *Riemann-Roch theorem*. Since Weil divisors on a curve are (roughly) in correspondence with line bundles on the curve, this result can alternatively be thought of as a result about the cohomology of line bundles on a curve. Serre duality will continue to be a crucial technical tool in this discussion.

In this discussion, by "curve" we mean an integral, separated, $1$-dimensional smooth scheme of finite type and proper over a field $k$. Note that in particular, the condition of being proper over a field $k$ implies that our curves are projective (Proposition II.6.7 of Hartshorne).

**Definition 4:** Let $X$ be a curve over a field $k$, with structure morphism $\varphi\colon X\to\operatorname{Spec}{k}$. Let $S$ be a finite set of dimension $0$ points of $X$, and for each $p\in S$ let $\varphi_p^{\sharp}\colon k\hookrightarrow k(p)$ be the extension of residue fields induced by $\varphi$. Let $D=\sum_{p\in S}{a_pp}$ be a divisor. Then we define the **degree of $D$** to be

$$\deg{D}:=\sum_{p\in S}{a_p[k(p):\varphi_p^{\sharp}(k)]}.$$

Notice that in the case that $k$ is algebraically closed, it follows from Exercise 5.3.F of Vakil that $k(p)\cong k$, and thus the degree of $D$ becomes the more familiar quantity $\sum_{p\in S}{a_p}$. This more general notion of degree will allow us to state a version of the Riemann--Roch theorem that works over arbitrary fields.

**Theorem 7 (Riemann--Roch):** Let $X$ be a curve over any field $k$ and let $D$ be a divisor on $X$. Then

$$\chi(X,\mathcal{O}(D))=\deg{D}+\chi(X,\mathcal{O}_X).$$

*Proof:* Write $D=\sum\_{p\in S}{a\_pp}$. We induct on $\sum\_{p\in S}{\|a\_p\|}$. In the base case, we have $D=0$. In this case, $\mathcal{O}(D)\cong\mathcal{O}\_X$, so the conclusion is immediate.

Now suppose the claim is true for some divisor $D$. Pick a (closed) point $p\in X$. Then $p$ is a closed subscheme of $X$ and thus gives the closed subscheme short exact sequence

$$0\longrightarrow\mathcal{O}(-p)\longrightarrow\mathcal{O}_X\longrightarrow\mathcal{O}_X|_p\longrightarrow0.$$

Note that $\mathcal{O}\_X\|\_p$ is simply a skyscraper sheaf of the residue field $k(p)$. So when we tensor the about exact sequence by the rank $$1$$ locally free sheaf $\mathcal{O}(D+p)$, this skyscraper sheaf will be preserved. Hence we have

$$0\longrightarrow\mathcal{O}(D)\longrightarrow\mathcal{O}(D+p)\longrightarrow\mathcal{O}_X|_p\longrightarrow0.$$

Now since Euler characteristic is additive on exact sequences, we have

$$\chi(X,\mathcal{O}(D+p))=\chi(X,\mathcal{O}(D))+\chi(X,\mathcal{O}_X|_p)=\deg{D}+\chi(X,\mathcal{O}_X)+\chi(X,\mathcal{O}_X|_p),$$

with the last equality following from the inductive hypothesis. But we can explicitly compute the Euler characteristic of $\mathcal{O}\_X\|\_p$ since we know it is just a skyscraper sheaf which is flabby. We have

$$\begin{split}
\deg{D}+\chi(X,\mathcal{O}_X)+\chi(X,\mathcal{O}_X|_p)&=\deg{D}+\chi(X,\mathcal{O}_X)+h^0(X,\mathcal{O}_X|_p)\\
&=\deg{D}+\chi(X,\mathcal{O}_X)+\dim_{k}{\Gamma(X,\mathcal{O}_X|_p)}\\
&=\deg{D}+\chi(X,\mathcal{O}_X)+\dim_{\varphi_p^{\sharp}(k)}{k(p)}\\
&=\deg{D}+\chi(X,\mathcal{O}_X)+[k(p):\varphi_p^{\sharp}(k)]\\
&=\deg{(D+p)}+\chi(X,\mathcal{O}_X).
\end{split}$$

This completes the induction. $\square$

The Riemann--Roch theorem is often written in various different ways. For example, we may observe that since since $X$ is projective, Serre duality applies and says $H^1(X,\mathcal{O}(D))\cong H^0(X,\omega_X\otimes\mathcal{O}(-D))^*$. Moreover, $\chi(X,\mathcal{O}_X)=1-p_a(X)$. So the Riemann--Roch theorem states

$$h^0(X,\mathcal{O}(D))-h^0(X,\mathcal{O}(K_X-D))=\deg{D}+1-p_a(X),$$

where $K_X$ is the canonical divisor of $X$. The useful consequence of this for us will be what results from letting $D=K_X$. Then we obtain

$$g(X)-1=\deg{K_X}+1-p_a(X),$$

and after an application of Theorem 3, we have the following formula for the degree of the canonical divisor.

**Corollary:** For a curve $X$, the degree of the canonical divisor is

$$\deg{K_X}=2g(X)-2.$$

We will need this formula to prove the Riemann--Hurwitz theorem.

### Ramification

We now discuss the important geometric concept of *ramification*. We continue to use the same definition of "curve" as in the section above.

Let $X$ be a locally Noetherian scheme. Consider a regular codimension $1$ point $p\in X$. The stalk $\mathcal{O}\_{X,p}$ at such a point is a regular local ring of dimension $1$. It is now a fact from commutative algebra that the stalk $\mathcal{O}\_{X,p}$ must be a discrete valuation ring.

**Definition 5:** Let $\pi\colon X\to Y$ be a finite morphism of curves over any field. Let $p\in X$ be a point, let $\pi^{\sharp}\colon\mathcal{O}\_{Y,\pi(p)}\to\mathcal{O}\_{X,p}$ be the induced map on stalks, and let $t$ be a uniformizing parameter of the DVR $\mathcal{O}\_{Y,\pi(p)}$. We define the **ramification index of $\pi$ at $p$**, denoted $e_p$, to be the valuation of $\pi^{\sharp}(t)$.

We also adopt some obvious terminology, such as *ramification locus* for the set of points $p$ for which $e_p>1$, *branch points* for the points that are in the image of the ramification locus, and so on. In order to geometrically understand the ramification and branch loci, we need to develop the following lemma.

Note that if $X$ and $Y$ are nonsingular varieties over a field $k$, and $\pi\colon X\to Y$ is a nonconstant finite morphism, Proposition II.6.7 and II.6.8 of Hartshorne imply that $\pi$ is surjective (and hence, dominant). It follows that there is an induced extension of function fields $K(Y)\hookrightarrow K(X)$. The *degree* of $\pi$ is defined to be the degree of this field extension. We say that $\pi$ is *separable* if the induced field extension is separable.

**Lemma 4:** Let $\pi\colon X\to Y$ be a finite separable morphism of irreducible varieties of the same dimension $n$ over a field $k$. Let $Y$ be smooth. Then there exists a short exact sequence of sheaves on $X$:

$$0\longrightarrow\pi^{*}(\Omega_{Y/k})\xrightarrow[]{\,\, \phi\,\,}\Omega_{X/k}\longrightarrow\Omega_{X/Y}\longrightarrow0.$$

*Proof:* Since $\pi$ is a morphism of $k$-schemes, we already have the relative cotangent sequence

$$\pi^{*}(\Omega_{Y/k})\xrightarrow[]{\,\, \phi\,\,}\Omega_{X/k}\longrightarrow\Omega_{X/Y}\longrightarrow0.$$

Since $Y$ is smooth, $\Omega_{Y/k}$ is a locally free sheaf of rank $n$ on $Y$, and thus $\pi^{\*}(\Omega_{Y/k})$ is a locally free sheaf of rank $n$ on $X$. Since localizations of torsion-free modules are themselves torsion-free, it follows that $\pi^{\*}(\Omega_{Y/k})$ is a torsion-free sheaf. 

Note that if $M$ is a torsion-free module over an integral domain $A$, then if the localization of $M$ at the zero ideal vanishes, we must have $M=0$. Therefore to show that $\phi$ is injective, it suffices to show that the stalk of the subsheaf $\ker{\phi}$ of $\pi^*(\Omega_{Y/k})$ at the generic point of $X$ is zero.

Let $\eta$ be the generic point of $X$. Stalkification is an exact functor, so we have the exact sequence

$$\pi^{*}(\Omega_{Y/k})_{\eta}\xrightarrow[]{\,\, \phi_{\eta}\,\,}(\Omega_{X/k})_{\eta}\longrightarrow(\Omega_{X/Y})_{\eta}\longrightarrow0.$$

Since $\Omega_{Y/k}$ and $\pi^{\*}(\Omega_{Y/k})$ both locally free of rank $n$, their stalks are isomorphic to $\mathcal{O}\_{X,\eta}^{\oplus n}$. Meanwhile, by Proposition II.8.2A of Hartshorne, localization commutes with taking modules of Kähler differentials, so we have $(\Omega_{X/Y})\_{\eta}\cong\Omega_{K(X)/K(Y)}$. But $K(Y)\hookrightarrow K(X)$ is a separable field extension, so for every $\alpha\in K(X)$, there exists a polynomial $f(t)\in (K(Y))[t]$ such that $f(\alpha)=0$ and $f'(\alpha)\neq0$. In particular, $f'(\alpha)\, d\alpha=0$ so $d\alpha=0$, hence $(\Omega_{X/Y})\_{\eta}\cong 0$. Therefore, the above exact sequence becomes

$$\mathcal{O}_{X,\eta}^{\oplus n}\xrightarrow[]{\,\, \phi_{\eta}\,\,}\mathcal{O}_{X,\eta}^{\oplus n}\longrightarrow 0\longrightarrow0.$$

In particular, $\phi_{\eta}$ is a surjection between free modules (in fact, vector spaces) of the same (finite) rank, so $\phi_{\eta}$ is an injection. $\square$

This lemma will allow us to say much more about ramification. As a first result, we can establish that in the reasonable cases, ramification only occurs finitely often.

**Theorem 8:** Let $\pi\colon X\to Y$ be a finite separable morphism of curves. Then $\pi$ is ramified at only finitely many points.

*Proof:* Let $p\in X$ be a point and let $u$ be a uniformizing parameter of the DVR $\mathcal{O}\_{X,p}$ and $t$ a parameter for $\mathcal{O}\_{Y,\pi(p)}$. Then the differential $dt$ generates $(\Omega\_{Y/k})\_{\pi(p)}$ as a $\mathcal{O}\_{Y,\pi(p)}$-module and $du$ generates $(\Omega\_{X/k})\_{p}$ as a $\mathcal{O}\_{X,p}$-module by II.8.7 and II.8.8 of Hartshorne. Then, $\pi^{\*}(dt)$ generates $\pi^{\*}(\Omega\_{Y/k})\_p$.

By exactness, the stalk $(\Omega_{X/Y})_p$ vanishes precisely when the map on stalks $\phi_p$ is surjective, where $\phi\colon \pi^{\*}(\Omega\_{Y/k})\to\Omega\_{X/k}$ is the map of sheaves in the short exact sequence from Lemma 4. This occurs if and only if $\phi_p(\pi^{\*}(dt))$ is a generator of $(\Omega\_{X/k})\_p$. Since $u$ is a uniformizing parameter for $\mathcal{O}\_{X,p}$, we may write $\pi^{\sharp}(t)=su^e$ for some unit $s\in\mathcal{O}\_{X,p}$ and nonnegative integer $e$. Hence, we may write

$$\phi_p(\pi^{*}(dt))=d(\pi^{\sharp}(t))=d(su^e)=u^e\, ds+esu^{e-1}\, du.$$

Here of course we interpret $e$ as the sum of $1$ with itself $e$ times in the ring $\mathcal{O}_{X,p}$. Since $du$ generates $(\Omega\_{X/k})_p$, we can write $ds=h\, du$ for some $h\in\mathcal{O}\_{X,p}$. Hence, the above equation becomes

$$\phi_p(\pi^{*}(dt))=u^{e-1}(hu+es)\, du.$$

If the characteristic of $k$ divides $e$, then the above becomes $hu^e\, du$, where $hu^e$ is in the maximal ideal $\langle u\rangle$ and thus not a unit. Hence, $\phi_p$ will not be surjective in this case.

On the other hand, if the characteristic of $k$ does not divide $e$, then $e\neq0$. Note also that since $X$ is a $k$-scheme, we may interpret $e$ as the germ of a nonzero constant function at $p$, so it is a unit in $\mathcal{O}_{X,p}$. Therefore, $hu+es$ is the sum of an element of the maximal ideal with a unit in a local ring, and thus is a unit. Therefore, in the case that $e\neq0$, we note that $\phi_p$ is surjective if and only if $e=1$.

Hence we have shown that $\phi\_p$ is surjective (so $(\Omega\_{X/Y})_p=0$) if and only if $\pi$ unramified at $p$. That is, the ramification locus of $\pi$ is precisely the support of $\Omega\_{X/Y}$. In the proof of Lemma 4, we showed that $\Omega\_{X/Y}$ is a torsion sheaf (its stalk at the generic point is zero). It follows (by Exercise 14.3.F(b) of Vakil) that the support of $\Omega\_{X/Y}$ lies in the complement of a dense open subset of $X$. That is, the ramification locus of $\pi$ lies in a finite set. $\square$

With Theorem 8 in hand, it now makes sense to make the following definition. We denote the length of a module $M$ by $\ell(M)$.

**Definition 6:** Let $\pi\colon X\to Y$ be a finite separable morphism of curves. We define the **ramification divisor of $\pi$**, denoted $R\_{\pi}$ to be the divisor $\sum_{p\in X}{\ell((\Omega\_{X/Y})\_p)p}$, and we define the **branch divisor of $\pi$**, denoted $B_{\pi}$, to be $\pi_{\*}(R_{\pi})$.

The proof of Theorem 8 also shows us that there are two kinds of ramification, and they behave somewhat differently on an algebraic level.

**Definition 7:** Let $\pi\colon X\to Y$ be a finite morphism of curves over the field $k$. Suppose $\pi$ is ramified at $p\in X$. If the characteristic of $k$ is zero or does not divide $e_p$, we say that the ramification of $\pi$ at $p$ is **tame**. Otherwise, we say that the ramification of $\pi$ at $p$ is **wild**.

We have already seen from the proof of Theorem 8 that $\pi$ is unramified at $p$ if and only if $\ell((\Omega\_{X/Y})\_p)=0$. This is why Definition 5 makes sense: it forces the formal sum in the definition of the ramification divisor to be a finite sum. So the length of the stalk of $\Omega_{X/Y}$ is a measure of the "amount" of ramification occurring at the point. However, it turns out that there is a quantitative difference between how tame and wild ramification are related to the length of the stalk.

**Theorem 9:** Let $\pi\colon X\to Y$ be a finite separable morphism of curves and let $p\in X$ be a point. Then

$$\ell((\Omega_{X/Y})_p)\geq e_p-1$$

with equality occuring if and only if $\pi$ is unramified at at $p$ (which occurs precisely when $e_p=1$), or if $\pi$ is tamely ramified at $p$.

*Proof:* We will use the notation from the proof of Theorem 8. Since $\pi^{\*}(dt)$ generates $\pi^{\*}(\Omega_{Y/k})_p$, there exists a unique element $g\in\mathcal{O}\_{X,p}$ such that $\phi_p(\pi^{\*}(dt))=g\, du$, where $\phi\colon \pi^{\*}(\Omega\_{Y/k})\to\Omega\_{X/k}$ is the map of sheaves in the short exact sequence from Lemma 4. More generally, we may write

$$\phi_p(h\, \pi^{*}(dt))=hg\, du$$

for any $h\in\mathcal{O}\_{X,p}$. This characterizes the map $\phi$. Hence by Lemma 4, we have the isomorphism of $\mathcal{O}\_{X,p}$-modules $(\Omega_{X/Y})\_p\cong\operatorname{coker}{\phi_p}\cong\mathcal{O}\_{X,p}/\langle g\rangle$. Thus,

$$\ell((\Omega_{X/Y})_p)=\ell\left(\frac{\mathcal{O}_{X,p}}{\langle g\rangle}\right)=v(g),$$

where $v(g)$ is the valuation of $g$. The last equality is a fact of commutative algebra and essentially follows from the pigeonhole principle: a chain of submodules of $\mathcal{O}\_{X,p}$ containing $g$, with length larger than $v(g)$, must contain repeated submodules since every element of $\mathcal{O}\_{X,p}$ is uniquely expressed as $su^k$ where $s$ is a unit.

Now, recall that we computed in the proof of Theorem 8 that

$$g=(hu+es)u^{e-1}$$

where $s$ is a unit in $\mathcal{O}_{X,p}$ and $e=e_p$ is the ramification index of $\pi$ at $p$. As we observed in the proof of Theorem 8, if $\pi$ is wildly ramified at $p$, this expression reduces to $hu^e\, du$, where $hu^e$ is not a unit, and thus $v(g)=v(hu^e)\geq e>e-1$. If $\pi$ is tamely ramified at $p$, we saw that $hu+es$ is a unit, and thus $v(g)=v((hu+es)u^{e-1})=e-1$. Finally, we saw in the proof of Theorem 8 that $\pi$ is unramified at $p$ if and only if $e=1$. $\square$

Note that from a geometric point of view, only tame ramification is relevant since this is all that can occur in characteristic zero. So what exactly is so "geometric" about this concept of ramification? Recall that the fiber of a finite morphism between curves will be finite set. The following technical lemma is Exercise 16.3.D(b) of Vakil, which shows that the degree of the morphism consists of contributions from each element of the fiber over any closed point.

**Lemma 5:** Let $\pi\colon X\to Y$ be a nonconstant finite morphism of curves and let $q\in Y$ be a closed point. For each point $p\in\pi^{-1}(\\{q\\})$, let $\overline{\pi}_p^{\sharp}\colon k(q)\hookrightarrow k(p)$ be the induced extension of residue fields. Then

$$\deg{\pi}=\sum_{p\in\pi^{-1}(\{q\})}{e_p[k(p):\overline{\pi}_p^{\sharp}(k(q))]}.$$

*Proof:* First, we call upon Proposition 16.3.5 of Vakil. $\pi$ is dominant, so it takes the generic point of $X$ to the generic point of $Y$. Since $\pi\_\*(\mathcal{O}_X)$ is locally free and stalkification is exact, it follows that the rank of $\pi\_\*(\mathcal{O}_X)$ will equal the rank of the stalk $K(X)$ with respect to the $K(Y)$-module structure induced by the map on stalks at the generic points $\pi\_{\eta}^{\sharp}\colon K(Y)\hookrightarrow K(X)$. That is, Hartshorne's definition of degree of a map (which is what we use) agrees with Vakil's: $\deg{\pi}=\operatorname{rank}{\pi\_\*(\mathcal{O}_X)}$.

Next, we need to observe that immediately from the definitions, we have the decomposition of the $\mathcal{O}\_{Y,q}$-module $(\pi_*(\mathcal{O}\_X))\_q$ given by

$$(\pi_*(\mathcal{O}_X))_q\cong\bigoplus_{p\in\pi^{-1}(\{q\})}{\mathcal{O}_{X,p}},$$

and thus it suffices to show that for a fixed choice of $p\in \pi^{-1}(\\{q\\})$, we have $\operatorname{rank}\_{\mathcal{O}\_{Y,q}}{\mathcal{O}_{X,p}}=e_p[k(p):\overline{\pi}_p^{\sharp}(k(q))]$.

Fix such a point $p$ and let $u_p$ be a uniformizing parameter of the DVR $\mathcal{O}\_{X,p}$, and let $t$ be a parameter for $\mathcal{O}\_{Y,q}$. Let us abbreviate $d\_p:=[k(p):\overline{\pi}_p^{\sharp}(k(q))]$ and let $\overline{w\_{p,1}},\overline{w\_{p,2}},\dots,\overline{w\_{p,d\_p}}$ be a $k(q)$-basis for $k(p)$. The maximal ideal of $\mathcal{O}\_{X,p}$ is generated by $u\_p$, so we may choose lifts $w\_{p,i}\in\mathcal{O}\_{X,p}$ of these basis elements whose valuations are zero (meaning they are units in $\mathcal{O}\_{X,p}$). Now it follows quickly by construction that the set of elements of the form $w\_{p,i}u\_p^{j}$, for $i\in\\{1,2,\dots,d\_p\\}$ and $j\in\\{0,1,\dots,e\_p-1\\}$, is a linearly independent $\mathcal{O}\_{Y,q}$-generating set of $\mathcal{O}\_{X,p}$. Therefore, $\operatorname{rank}\_{\mathcal{O}\_{Y,q}}{\mathcal{O}\_{X,p}}=e\_pd\_p$ as claimed. $\square$

**Theorem 10:** Let $\pi\colon X\to Y$ be a finite morphism of curves over an algebraically closed field $k$. Let $q\in Y$ be chosen so that the ramification of $\pi$ at every point in the fiber $\pi^{-1}(\\{q\\})$ is tame. Then,

$$|\pi^{-1}(\{q\})|=\deg{\pi}-\deg{B_{\pi}|_q}.$$

*Proof:* Since $q$ is a closed point and $p$ is a closed point for every $p$ in the fiber over $q$, it follows (Exercise 5.3.F of Vakil) that both $k(p)$ and $k(q)$ are finite (and thus, algebraic) extensions of $k$. But $k$ is algebraically closed, so $k(p)\cong k(q)\cong k$ and thus in the notation of Lemma 5, $d_p=1$ for all $p\in \pi^{-1}(\\{q\\})$. Therefore, Lemma 5 and Theorem 8 yield

$$\deg{\pi}=\sum_{p\in \pi^{-1}(\{q\})}{e_p}=\sum_{p\in \pi^{-1}(\{q\})}{[(e_p-1)+1]}=\deg{B_{\pi}|_q}+|\pi^{-1}(\{q\})|.$$

$\square$

This finally gives us a geometric interpretation of ramification (at least in characteristic zero where all ramification is tame). Generically, the size of the fibers of $\pi$ is $\deg{\pi}$. However, over branch points, the number is smaller. Hence we may interpret $\pi$ as a sort of generically $(\deg{\pi})$-sheeted cover, with ramification points just being places where these sheets collide.

<div style="text-align: center;">
<img src="/myassets/images/Theory-of-curves/ramification.png" alt="diagram" width="700px">
</div>

In the depiction of tame ramification over an algebraically closed field above, $\deg{\pi}=4$ which is the size of the generic fiber, the ramification divisor is $R_{\pi}=2p_1+p_2+p_3+p_4+p_5$, the branch divisor is $B_{\pi}=2q_1+q_2+q_3+2q_4$, and we can see that the formula for the size of the fibers from Theorem 10 holds true. In general, we see that the ramification index at any point in $X$ measures precisely the number of sheets passing through that point. A canonical example of this would be the map $z\mapsto z^2$ on the complex plane to itself. Every nonzero complex number has two square roots, but the map is ramified at zero. See <a href="https://en.wikipedia.org/wiki/Riemann_surface#Algebraic_curves" target="_blank">here</a> for some nice visuals of Riemann surfaces arising as graphs of algebraic functions from the complex plane to itself.

### The Riemann--Hurwitz Formula

We can finally state and prove the main result.

**Theorem 11 (Riemann--Hurwitz):** Let $\pi\colon X\to Y$ be a finite separable morphism of curves. Then

$$\boxed{2g(X)-2=(\deg{\pi})(2g(Y)-2)+\deg{R_{\pi}}}.$$

*Proof:* We start by considering the ramification divisor $R_{\pi}$ as a closed subscheme of $X$. Let $\iota\colon R_{\pi}\to X$ be the closed embedding. This gives the short exact sequence

$$0\longrightarrow\mathcal{O}_X(-R_{\pi})\longrightarrow\mathcal{O}_X\longrightarrow\iota_*(\mathcal{O}_{R_{\pi}})\longrightarrow0.$$

Taking determinants in this exact sequence, we find that $\mathcal{O}\_X(-R_{\pi})\otimes\det{\iota\_{\*}(\mathcal{O}\_{R\_{\pi}})}\cong\mathcal{O}\_X$, which means $\det{\iota\_{\*}(\mathcal{O}\_{R\_{\pi}})}\cong\mathcal{O}\_X(R\_{\pi})$. We also see from the proof of Theorem 8 that the structure sheaf of $R_{\pi}$ is isomorphic to the restriction of $\Omega_{X/Y}$ to $R_{\pi}$. Since $R_{\pi}$ is the support of $\Omega_{X/Y}$, we have that

$$\Omega_{X/Y}=\iota_*((\Omega_{X/Y})|_{R_{\pi}})\cong\iota_*(\Omega_{R_{\pi}}),$$

hence we have shown that $\det{\Omega_{X/Y}}\cong\mathcal{O}\_X(R\_{\pi})$. Now we can take determinants in the short exact sequence of Lemma 4. This gives

$$\det{\pi^*(\Omega_{Y/k})}\otimes\det{\Omega_{X/Y}}\cong\det{\Omega_{X/k}},$$

For a finite morphism of curves $\pi$, determinant will commute with pullback. Hence the above completely simplifies to $\pi^*(\omega\_Y)\otimes\mathcal{O}\_X(R\_{\pi})\cong\omega\_X$. Taking the associated divisors, we have the linear equivalence:

$$K_X\sim\pi^*(K_Y)+R_{\pi}.$$

This is sometimes known as the *strong Riemann--Hurwitz theorem*. Our result follows from this by taking the degrees of both sides. By our corollary to the Riemann--Roch theorem, we know that $\deg{K_X}=2g(X)-2$ and $\deg{K_Y}=2g(Y)-2$. By Proposition II.6.9 of Hartshorne, the degree of the pullback is the product of the degree of the divisor with the degree of the map. Thus the formula follows. $\square$

So ultimately, given a reasonable map $\pi\colon X\to Y$ of curves, the genera of the curves $X$ and $Y$ must be related to the degree and ramification of $\pi$.

A nonconstant morphism between curves (under our definition of "curve") must be finite by Proposition II.6.8 of Hartshorne. Moreover, in characteristic $0$, every finite morphism is automatically separable since the formal derivative of any nonzero nonconstant polynomial will be nonzero. Therefore, we are now in a position to extend Theorem 1 to the setting of any base field $k$ of characteristic $0$.

*Proof 2 of Theorem 1:* Suppose that $k$ is a field of characteristic $0$ and $\pi\colon\mathbb{P}^1\_k\dashrightarrow F\_k^n$ is a dominant rational map. By the curve-to-projective extension theorem, this promotes to a genuine finite morphism $\tilde{\pi}\colon \mathbb{P}^1\_k\to F\_k^n$. Moreover, this morphism is separable since $k$ has characteristic $0$. Hence, the Riemann--Hurwitz theorem tells us that

$$2g(\mathbb{P}_k^1)-2=(\deg{\tilde{\pi}})(2g(F_k^n)-2)+\deg{R_{\tilde{\pi}}}.$$

By Theorem 2, Theorem 3, and the corollary to Theorem 6, we can fill out the genera of the two curves, so the above equation becomes

$$-2=(\deg{\tilde{\pi}})((n-1)(n-2)-2)+\deg{R_{\tilde{\pi}}}.$$

But $n\geq 3$, so $(n-1)(n-2)-2\geq0$. Moreover, $\deg{\tilde{\pi}}\geq1$ and $\deg{R_{\tilde{\pi}}}\geq0$. Therefore the right hand side of the equation above should be nonnegative, a contradiction. $\square$

## Parameterized Rational Solution Sets

Now that we have thoroughly discussed Theorem 1, let us discuss its relationship with Fermat's last theorem. Classically, we are interested in integer (or equivalently, rational) solutions to the equation $x^n+y^n=z^n$ for $n>2$. When $n=2$, the problem is very simple. There are infinitely many solutions to the equation, and they are the Pythagorean triples. In fact, the entire infinite family of solutions can be parameterized by the projective line as follows.

**Theorem 12:** Let $k$ be a field of characteristic not equal to $2$. Then the conic $x^2+y^2=z^2$ in $\mathbb{P}^2_k$ is isomorphic to the projective line $\mathbb{P}^1_k$.

*Proof:* Let $C$ be the conic. Note that $[-1,0,1],[1,0,1]\in C$. Put $U=C\setminus\\{[-1,0,1]\\}$ and $V=C\setminus\\{[1,0,1]\\}$. Let us define a map $\psi\_U\colon U\to\mathbb{P}^1\_k$ by $\psi\_U([x,y,z])=[x+z,y]$. Note that this is well-defined by the definition of $U$—it will never be the case that both $y$ and $x+z$ vanish on $U$. Similarly, we may define a map $\psi\_V\colon V\to\mathbb{P}^1\_k$ by $\psi\_V([x,y,z])=[y,z-x]$. Of course, on the overlap $U\cap V$, we may note that since $y^2=(x+z)(z-x)$, we have that $\psi\_U\|\_{U\cap V}=\psi\_V\|\_{U\cap V}$. So $\psi\_U$ and $\psi\_V$ glue to a morphism $\psi\colon C\to\mathbb{P}^1_k$.

An inverse map $\varphi\colon\mathbb{P}^1\_k\to C$ can be defined by $\varphi([x,y])=[x^2-y^2,2xy,x^2+y^2]$. Note then that if $x\neq0$, we have $[2x^2,2xy]=[x,y]$ and if $y\neq0$, we have $[2xy,2y^2]=[x,y]$. Hence, $\psi\circ\varphi$ is the identity. For similar reasons, we can see that $\varphi\circ\psi$ is the identity. Note that this argument works as long as $2\neq0$, which occurs as long as $k$ does not have characteristic 2. $\square$

The isomorphism given in the theorem above yields a parameterization of all rational Pythagorean triples. Select $k=\mathbb{Q}$ above. Then by the isomorphism above, any Pythagorean triple $a,b,c$ must form a point in projective space $[a,b,c]$ equal to $[x^2-y^2,2xy,x^2+y^2]$ for some choice of point $[x,y]\in\mathbb{P}_{\mathbb{Q}}^1$. In particular, by scaling the homogeneous coordinates and clearing the denominators, we may assume without loss of generality that $x$ and $y$ are integers. By scaling and factoring out the greatest common divisor, we may also assume that $x$ and $y$ are coprime. Then, we have

$$\begin{cases}
a=\lambda(x^2-y^2)\\
b=2\lambda xy\\
c=\lambda(x^2+y^2),
\end{cases}$$

where $\lambda$ is a rational number, say $\frac{p}{q}$ for coprime integers $p$ and $q$. This alone is good enough, but lets push this further to something you would encounter classically.

Since $b=2\lambda xy$ is an integer, we must have $q\mid 2xy$. Let $s$ be a prime factor of $q$. If $s\mid y$, we have that $s\mid y^2$, so that $s\mid x^2$, since $c=x^2+y^2$ is an integer. So $s\mid x$, violating our assumption that $x$ and $y$ are coprime. Hence, $s\nmid y$, and similarly $s\nmid x$. It follows that $s=2$, so $q$ is a power of $2$.

Suppose that $x$ and $y$ are not both odd. Then since they are coprime, one of them is odd and the other is even. Therefore, $x^2+y^2$ is odd. But $c=\lambda(x^2+y^2)$ must be an integer and $q$ is a power of $2$. Hence we must have $q=1$ in this situation, so $\lambda$ can be taken to be an integer.

If $x$ and $y$ are both odd, then $a$, $b$, and $c$ are even. This means that we can write $a=2^i\alpha$, $b=2^j\beta$, and $c=2^k\gamma$, for odd numbers $\alpha$, $\beta$, and $\gamma$, and positive integers $i$, $j$, and $k$. Note that 

$$2^{2i}\alpha^2+2^{2j}\beta^2=2^{2k}\gamma^2.$$

Without loss of generality, suppose $i\leq j$. It is impossible for $k<i$, since if this were the case, dividing both sides of the above equation by $2^{2k}$, the above equation would have an even left hand side but an odd right hand side. Hence, when we divide the above equation by $2^{2i}$ to obtain

$$\alpha^2+2^{2(j-i)}\beta^2=2^{2(k-i)}\gamma^2.$$

we have obtained the Pythagorean triple $\alpha$, $2^{j-i}\beta$, and $2^{k-i}\gamma$. Note that we must have $j-i>0$, since otherwise we have a Pythagorean triple where both summands are odd, which is impossible as is seen by reducing the Pythagorean equation modulo $4$. Hence, $2^{j-i}\beta$ is genuinely even. This new Pythagorean triple is obtained by some homogeneous coordinate $[\tilde{x},\tilde{y}]$ where $\tilde{x}$ and $\tilde{y}$ are coprime integers. We may write

$$\begin{cases}
\alpha=\tilde{\lambda}(\tilde{x}^2-\tilde{y}^2)\\
2^{j-i}\beta=2\tilde{\lambda}\tilde{x}\tilde{y}\\
2^{k-i}\gamma=\tilde{\lambda}(\tilde{x}^2+\tilde{y}^2),
\end{cases}$$

where $\tilde{\lambda}$ is a rational number. By our past argument a few paragraphs above, we know that the denominator $\tilde{q}$ of $\tilde{\lambda}$ must be a power of $2$. Suppose $\tilde{x}$ and $\tilde{y}$ are both odd. Since $2^{j-i}\beta=2\tilde{\lambda}\tilde{x}\tilde{y}$ needs to be an integer, it follows that $\tilde{q}=2$ or $\tilde{q}=1$ are the only positive choices for $\tilde{q}$. If $\tilde{q}=2$, since $\tilde{x}^2-\tilde{y}^2$ must be a multiple of $4$, it follows that $\alpha=\tilde{\lambda}(\tilde{x}^2-\tilde{y}^2)$ is a multiple of $2$, a contradiction. Therefore, $\tilde{q}=1$ if $\tilde{x}$ and $\tilde{y}$ are both odd, so $\tilde{\lambda}$ can be taken to be an integer. If $\tilde{x}$ and $\tilde{y}$ are not both odd, by our past argument a few paragraphs above, it follows that $\tilde{q}=1$. Hence, $\tilde{\lambda}$ can be taken to be an integer in every case.

Hence in the case that $x$ and $y$ are both odd, we can replace $x$ and $y$ with integers $\tilde{x}$ and $\tilde{y}$ that are not both odd, and then select $\lambda$ to be an integer: $\lambda=2^i\tilde{\lambda}$.

To sum up, we have shown that $x$ and $y$ can be judiciously chosen so that $\lambda$ can always be taken to be an integer, and that these $x$ and $y$ can be chosen to not both be odd. That is, the Pythagorean triples are generated by the triples of the form

$$\begin{cases}
\lambda(x^2-y^2)\\
2\lambda xy\\
\lambda(x^2+y^2),
\end{cases}$$

where $x$ and $y$ are coprime integers, not both odd, and $\lambda$ is an integer. This is the classical <a href="https://en.wikipedia.org/wiki/Pythagorean_triple#Generating_a_triple" target="_blank">Euclid's formula</a> for generating Pythagorean triples, and it essentially falls out of the isomorphism between the conic $x^2+y^2=z^2$ and the projective line.

Theorem 1 establishes that at least over the complex numbers, there is no isomorphism between the projective line and the curve $x^n+y^n=z^n$ for $n>3$. Even though this is a statement over the complex numbers, by descent it has implications for the nature of rational solutions to the equation $x^n+y^n=z^n$ for $n>3$. Hence, the low brow proof shown above, which only works over $\mathbb{C}$, is sufficient for what follows about rational solutions.

The relevant result to show this is the following characterization of dominant morphisms.

**Proposition 7.5.8 (Vakil)/Lemma 29.8.8 (Stacks):** A morphism $f\colon X\to Y$ between integral $k$-schemes is dominant if and only if the induced map on stalks $\mathcal{O}\_{Y,f(x)}\to\mathcal{O}\_{X,x}$ is injective for any $x\in X$.

Fermat's last theorem asserts that there are no rational solutions to $x^n+y^n=z^n$ for $n>2$. This is a far stronger statement than anything we have discussed which of course requires much more machinery. However, we have seen in the $n=2$ case that a dominant rational map from $\mathbb{P}^1_{\mathbb{Q}}$ to the Fermat curve over $\mathbb{Q}$ yields an infinite family of rational solutions to $x^n+y^n=z^n$ parameterized by the projective line.

Suppose such an infinite family of rational solutions exists for $n>3$. That is, suppose there exists a dominant rational map from $\mathbb{P}\_{\mathbb{Q}}^1$ to the Fermat curve over $\mathbb{Q}$ for $n>2$. Let us denote the Fermat curve over $\mathbb{Q}$ as $F\_{\mathbb{Q}}^{n}$. As we have seen with the curve-to-projective extension theorem, this extends to a dominant morphism $\phi_{\mathbb{Q}}\colon\mathbb{P}\_{\mathbb{Q}}^1\to F\_{\mathbb{Q}}^{n}$. By the Proposition/Lemma above, the induced morphism on function fields $\phi\_{\mathbb{Q}}^{\sharp}\colon K(F\_{\mathbb{Q}}^{n})\to K(\mathbb{P}\_{\mathbb{Q}}^1)$ is injective.

Now we extend the base field to $\mathbb{C}$. Applying the change of base functor to the morphism $\phi\_{\mathbb{Q}}$, we obtain the morphism $\phi\_{\mathbb{C}}\colon\mathbb{P}\_{\mathbb{C}}^1\to F\_{\mathbb{C}}^1$. Looking at this new morphism on the stalks at the points corresponding to the generic points over $\mathbb{Q}$ amounts to performing an extension of scalars via the functor $-\otimes\_{\mathbb{Q}}\mathbb{C}$ on the map $\phi\_{\mathbb{Q}}^{\sharp}$. Since $\mathbb{Q}$ is a field, it is automatic that $\mathbb{C}$ is flat as a $\mathbb{Q}$-module since it is a vector space (free module). Therefore, the functor $-\otimes\_{\mathbb{Q}}\mathbb{C}$ is exact and so the injectivity of $\phi\_{\mathbb{Q}}^{\sharp}$ is preserved after base change. It follows from the Proposition/Lemma above, $\phi\_{\mathbb{C}}$ is a dominant morphism. But such a thing cannot exist by Theorem 1.

So perhaps one moral of this story is that an extremely weak form of Fermat's last theorem---that there is no $\mathbb{P}^1$-parameterized family of rational points on the Fermat curve for $n>2$---is true for entirely geometric reasons.