---
layout: post
title: "The Hodge decomposition for curves"
date: 2025-12-11 22:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

The Hodge decomposition for compact Kähler manifolds states that if $X$ a compact Kähler manifold, then the cohomology of $X$ decomposes canonically
\\[H^k(X,\mathbb{C})=\bigoplus\_{p+q=k}{H^{p,q}(X)},\\]
and moreover it is immediate that $H^{p,q}(X)=\overline{H^{q,p}(X)}$. Here, $H^{p,q}(X)$ is the space of cohomology classes of $(p,q)$-forms. Showing this decomposition holds is not a short story and it requires some deep analytic results about elliptic operators. However, one can show that a simple form of this decomposition holds more organically in the case that $X$ is a compact connected complex curve (a Riemann surface). That is, one may show that for such an $X$, we have
\\[\boxed{H^1(X,\mathbb{C})\cong H^0(X,\Omega_X^1)\oplus H^1(X,\mathcal{O}_X),}\\]
Here, $\mathcal{O}_X$ is the structure sheaf of holomorphic functions on $X$ and $\Omega_X^1$ is the sheaf of holomorphic $1$-forms.

Making the identifications $H^0(X,\Omega_X^1)\cong H^{1,0}(X)$ and $H^1(X,\mathcal{O}_X)\cong H^{0,1}(X)$ so that the above decomposition looks more like the classical Hodge decomposition requires more, since the general fact $H^{p,q}(X)\cong H^q(X,\Omega_X^p)$, where $\Omega_X^p$ is the sheaf of <a href="https://en.wikipedia.org/wiki/Complex_differential_form#Holomorphic_forms" target="_blank">holomorphic $p$-forms</a>, requires some elliptic operator theory. We can also show that in our special case of a compact connected complex curve, $H^1(X,\mathcal{O}_X)\cong\overline{H^0(X,\Omega_X^1)}$, provided that we may assume that $H^1(X,\mathcal{O}_X)\cong H^{0,1}(X)$. Without this, we would have trouble interpreting the degree $1$ sheaf cohomology $H^1(X,\mathcal{O}_X)$. Theorems 4.49 and 4.50 of Voisin give some interpretations of sheaf cohomology in degree $1$. For example, using Čech cohomology, if $\mathcal{O}_X^{\times}$ is the sheaf of nonvanishing holomorphic functions on $X$, we can see that $H^1(X,\mathcal{O}_X^{\times})$ can be interpreted as the <a href="https://en.wikipedia.org/wiki/Picard_group" target="_blank">Picard group</a> of $X$.

Note that any complex curve is automatically Kähler, since the real dimension is $2$ and so every $2$-form is immediately closed which makes any Hermitian metric on a complex curve Kähler. Therefore, a compact complex curve is a special case to which the Hodge decomposition *should* apply.

We start by fixing a compact connected complex curve $X$. In particular, we are dealing with a *closed* manifold, which is a compact manifold without boundary. This fact will be relevant for us later. Let $\mathcal{O}_X$ be the sheaf of holomorphic functions on $X$ and let $\Omega_X^1$ be the sheaf of holomorphic 1-forms. Since $X$ is a curve, any section of this sheaf can be expressed locally as simply $f\, \mathrm{d}z$ where $f$ is a holomorphic function and $z$ is a local coordinate.

The complex derivative of any holomorphic function is itself holomorphic, so exterior differentation furnishes a morphism of sheaves $d\colon\mathcal{O}_X\to\Omega_X^1$. From complex analysis (say, Cauchy's theorem) we know that in simply connected neighborhoods, holomorphic functions have antiderivatives. This means that every section of $\Omega_X^1$ is at least locally exact. This is a special case of the more general <a href="https://en.wikipedia.org/wiki/Poincar%C3%A9_lemma" target="_blank">Poincaré lemma</a>. In any case, this means that $d$ is surjective on stalks—that is, it is an epimorphism of sheaves. Of course, the kernel of $d$ is the sheaf of locally constant functions $\underline{\mathbb{C}}$. Since $X$ is connected, this is the sheaf of constant functions. Hence we have a short exact sequence of sheaves:
\\[0\longrightarrow\underline{\mathbb{C}}\longrightarrow\mathcal{O}_X\xrightarrow[]{\,\, d\,\,}\Omega_X^1\longrightarrow0.\\]
This short exact sequence induces the following long exact sequence in sheaf cohomology:
<div style="text-align: center;">
<img src="/myassets/images/Hodge-decomposition-for-curves/cohomologyles.png" alt="diagram" width="700px">
</div>
We can fill out a few of modules in the above diagram.
1. Since $X$ is connected, we have $H^0(X,\underline{\mathbb{C}})\cong\mathbb{C}$.
1. Since $X$ is a compact Riemann surface, we have $H^0(X,\mathcal{O}_X)\cong\mathbb{C}$ by <a href="https://en.wikipedia.org/wiki/Liouville%27s_theorem_(complex_analysis)#On_compact_Riemann_surfaces" target="_blank">Liouville's theorem</a>.
1. $X$ is a complex curve, so its canonical bundle is just $\Omega_X^1$. Hence, by Serre duality
\\[H^1(X,\Omega_X^1)\cong H^0\left(X,(\Omega_X^1)^{\*}\otimes \Omega_X^1\right)^{\*}\cong H^0(X,\mathcal{O}_X)^{\*}\cong\mathbb{C}.\\]
1. Since $X$ is a complex manifold, <a href="https://math.stackexchange.com/questions/1817959/almost-complex-manifolds-are-orientable" target="_blank">it is orientable</a>. Therefore, Poincaré duality applies and it tells us that $H^2(X,\mathbb{Z})\cong H^0(X,\mathbb{Z})$. The Abelian group $\mathbb{C}$ is torsion-free as a $\mathbb{Z}$-module and thus by the universal coefficient theorem, we have $H^2(X,\underline{\mathbb{C}})\cong H^0(X,\underline{\mathbb{C}})$. Alternatively, we may use Poincaré duality with $\mathbb{C}$-coefficients directly because $\mathbb{Z}$-orientability implies $\mathbb{C}$-orientability.
1. By <a href="https://en.wikipedia.org/wiki/Dolbeault_cohomology#Dolbeault's_theorem" target="_blank">Dolbeault's theorem</a>, we have $H^2(X,\mathcal{O}\_X)\cong H\_{\overline{\partial}}^{0,2}(X)\cong 0$ since $X$ has complex dimension $1$ so its second Dolbeault cohomology vanishes.

Hence, the long exact sequence above becomes
<div style="text-align: center;">
<img src="/myassets/images/Hodge-decomposition-for-curves/dia2.png" alt="diagram" width="700px">
</div>
This diagram consists of maps of $\mathbb{C}$-modules, that is, complex vector spaces. Therefore, the injectivity of $\tilde{\iota}$ and the surjectivity of $\tilde{\delta}$ automatically imply that they are isomorphisms. Hence, the long exact sequence above induces the short exact sequence
\\[0\longrightarrow H^0(X,\Omega_X^1)\longrightarrow H^1(X,\underline{\mathbb{C}})\longrightarrow H^1(X,\mathcal{O}_X)\longrightarrow0.\\]
This is a short exact sequence of complex vector spaces so it splits. So we already have the Hodge decomposition
\\[H^1(X,\underline{\mathbb{C}})\cong H^0(X,\Omega_X^1)\oplus H^1(X,\mathcal{O}_X),\\]
where of course, standard results of sheaf cohomology tell us that $H^1(X,\underline{\mathbb{C}})\cong H^1(X,\mathbb{C})$.

Now we show that conjugation yields an isomorphism $\overline{H^0(X,\Omega_X^1)}\to H^{0,1}(X)$. More precisely, this is the map that will send the cohomology class of a form $[\alpha]\in\overline{H^0(X,\Omega_X^1)}$ to the class $[\overline{\alpha}]$. Note that this is indeed a complex-linear map because of how scalar multiplication is defined in the <a href="https://en.wikipedia.org/wiki/Complex_conjugate_of_a_vector_space" target="_blank">conjugate vector space</a> $\overline{H^0(X,\Omega_X^1)}$.

First we show that this map is an injection. Let $[\alpha]\in\overline{H^0(X,\Omega_X^1)}$ be in the kernel of conjugation, where $\alpha$ is a holomorphic $1$-form. This means that $\overline{\alpha}$ must be an exact form, say $\overline{\alpha}=df$ for some smooth function $f$. Notice that $\alpha$ itself must also be exact, since
\\[d\alpha=\partial\alpha+\overline{\partial}\alpha=0+0=0,\\]
where $\partial\alpha$ vanishes since $\alpha$ is a $(1,0)$-form and $X$ is of complex dimension $1$, and $\overline{\partial}\alpha=0$ since $\alpha$ is holomorphic. Therefore, we may compute the square of the $L^2$-norm of $\alpha$ as follows:
\\[\\|\alpha\\|\_{L^2}^2=\int\_{X}{\alpha\wedge\overline{\alpha}}=\int\_{X}{\alpha\wedge df}=\int\_{X}{d(\alpha\wedge f)}=0,\\]
with the last equality following from Stokes' theorem along with the fact that $X$ has no boundary. Therefore, $\alpha=0$ so the kernel is trivial.

Finally, observe that
\\[\overline{H^0(X,\Omega_X^1)}\cong H^0(X,\Omega_X^1)\cong H^{1,0}(X)\cong H^{0,1}(X)^*\cong H^{0,1}(X)\cong H^1(X,\mathcal{O}_X),\\]
with the middle isomorphism coming from Serre duality, and the remaining isomorphisms coming from the standard results from Hodge theory that $H^{p,q}(X)\cong H^q(X,\Omega_X^p)$ and that these spaces are finite-dimensional. In particular, since conjugation is an injective linear map between two finite-dimensional vector spaces of the same dimension, it must be an isomorphism, so we are done.


