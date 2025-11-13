---
layout: post
title: "Symbol of an operator"
date: 2025-7-20 12:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Let \\(E\\) and \\(F\\) be complex \\(C^{\infty}\\) vector bundles over a differentiable manifold \\(X\\). Let \\(\underline{C}^{\infty}(E)\\) and \\(\underline{C}^{\infty}(F)\\) be the corresponding sheaves of smooth sections, and let \\(P\colon\underline{C}^{\infty}(E)\to\underline{C}^{\infty}(F)\\) be a \\(\mathbb{C}\\)-linear morphism of sheaves. This discussion works the same over \\(\mathbb{R}\\) instead of \\(\mathbb{C}\\) as well.

We say that \\(P\\) is a <a href="https://en.wikipedia.org/wiki/Differential_operator" target="_blank">**differential operator of order \\(k\\)**</a> if, in common trivializations over open sets \\(U\subseteq X\\) with coordinates \\(x\_1,x\_2,\dots,x\_n\\) where
\\[E\|\_U\cong U\times\mathbb{C}^p,\qquad F\|\_U\cong U\times\mathbb{C}^q,\\]
we have \\(P((\alpha\_1,\alpha\_2,\dots,\alpha\_p))=(\beta\_1,\beta\_2,\dots,\beta\_q)\\) with
\\[\beta\_i=\sum\_{I,j}{P\_{I,i,j}\frac{\partial\alpha\_j}{\partial x\_I}}\\]
where the coefficients \\(P\_{I,i,j}\\) are \\(C^{\infty}\\), and zero for \\(\|I\|>k\\), with at least one coefficient \\(P\_{I,i,j}\\) nonzero for \\(\|I\|=k\\).

Let us take a look at the order \\(k\\) part of \\(P\\) in the trivialization coordinates. This operator \\(P^k\\) can be written as a matrix
\\[[P^k\_{i,j}]=\sum\_{\|I\|=k}{P\_{I,i,j}\frac{\partial}{\partial x\_I}}.\\]
We claim that the factors \\(\frac{\partial}{\partial x\_I}\\) transform like sections of the \\(k\\)th symmetric power bundle \\(S^k(T(X))\\) under changes of coordinates on \\(X\\). Indeed, let \\(U\\) be an open subset on which both \\(E\\) and \\(F\\) are trivial, and let \\(x\_1,x\_2,\dots,x\_n\\) and \\(y\_1,y\_2,\dots,y\_n\\) be coordinate systems on \\(U\\). Let \\(\Phi\colon U\to U\\) be the change of coordinates with \\(\Phi(x\_i)=y\_i\\). Observe that by the chain rule,
\\[\frac{\partial}{\partial x\_i}=\sum\_{j}{\frac{\partial\Phi\_j}{\partial x\_i}\frac{\partial}{\partial y\_j}},\\]
hence as sections of \\(S^k(T(X))\\) we have
\\[\prod\_{\ell=1}^{k}{\frac{\partial}{\partial x\_{i\_{\ell}}}}=\prod\_{\ell=1}^{k}{\sum\_{j=1}^{n}{\frac{\partial\Phi\_j}{\partial x\_{i\_{\ell}}}\frac{\partial}{\partial y\_j}}}.\\]
We can verify that the right hand side of the above equation is also equivalent to \\(\frac{\partial}{\partial x\_{i\_1}\partial x\_{i\_2}\dots\partial x\_{i\_k}}\\) by induction on \\(k\\). We have already established the base case of \\(k=1\\). Suppose the claim is true for some \\(k\\). Put \\(S\_{\ell}=\sum\_{j=1}^{n}{\frac{\partial\Phi\_j}{\partial x\_{i\_{\ell}}}\frac{\partial}{\partial y\_j}}\\). Then by the Leibniz rule, we have
\\[\frac{\partial}{\partial x\_{i\_1}\partial x\_{i\_2}\dots\partial x\_{i\_{k+1}}}=\sum\_{m=1}^{k}{\frac{\partial S\_m}{\partial x\_{i\_{k+1}}}\prod\_{m\neq \ell=1}^{k}{S\_{\ell}}}.\\]
By chain rule, we have
\\[\frac{\partial S\_m}{\partial x\_{i\_{k+1}}}=\sum\_{t=1}^{n}{\frac{\partial\Phi\_t}{\partial x\_{i\_m}}\sum\_{s=1}^{n}{\frac{\partial\Phi\_s}{\partial x\_{i\_{k+1}}}\frac{\partial}{\partial y\_s\partial y\_j}}}.\\]
Combining this with the above, a moment's thought reveals that we will have completed the induction.

A similar calculation will show that the matrix of coefficients \\([P\_{I,i,j}]\\) describes a morphism of bundles \\(E\|\_U\to F\|\_U\\) and these matrices transform in the same way as a section of \\(\mathrm{Hom}{(E,F)}\\) upon changes of trivialization. Therefore, the \\(k\\)th order data of \\(P\\) is captured by a section \\(\sigma\_P\\) of the bundle \\(\mathrm{Hom}{(E,F)}\otimes S^k(T(X))\\). This section \\(\sigma\_P\\) is known as the **symbol of the operator** \\(P\\).

Now we may recall two facts from linear algebra.

  1. For vector spaces \\(V\\) and \\(W\\), if \\(V\\) is finite dimensional, then \\(\mathrm{Hom}{(V,W)}\cong V^*\otimes W\\).
  2. For a vector space \\(V\\) over a field of characteristic 0, we have that \\(S^k(V^\*)\cong S^k(V)^\*\\). See <a href="https://virtualmath1.stanford.edu/~conrad/diffgeomPage/handouts/tensor.pdf" target="_blank">here</a> and <a href="https://math.stackexchange.com/questions/5011003/can-the-dual-of-a-symmetric-power-be-shown-to-the-the-symmetric-power-of-the-dua" target="_blank">here</a> as references.


From these facts, it follows that
\\[\mathrm{Hom}{(E,F)}\otimes S^k(T(X))\cong\mathrm{Hom}{(S^k(T^*(X)),\mathrm{Hom}{(E,F)})}.\\]
The symbol \\(\sigma\_P\\) is often interpreted as a section of the bundle on the right hand side. This means that at each point \\(x\in X\\), we can interpret \\(\sigma\_P\\) as giving homogeneous map of degree \\(k\\) from the cotangent space to \\(\mathrm{Hom}{(E\_x,F\_x)}\\). If \\(\sigma\_{P,x}(\alpha\_x)\colon E\_x\to F\_x\\) is injective for each \\(x\\) and nonzero covector \\(\alpha\_x\\), then we say that \\(P\\) is **elliptic**.