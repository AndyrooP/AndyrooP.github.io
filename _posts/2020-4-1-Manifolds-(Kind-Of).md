---
layout: post
title: "Manifolds (Kind Of)"
date: 2020-4-1 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
Suppose that we have a function \\(f\colon U\to\mathbb{R}^m\\), where \\(U\\) is an open subset of \\(\mathbb{R}^n\\). Then, we define a *regular point* to be a point \\(\vec{c}\in U\\) such that the derivative of \\(f\\) at \\(\vec{c}\\) is surjective.

Suppose \\(f(\vec{c})=\vec{b}\\). Then, the implicit function theorem states that in a neighborhood of \\(c\\), the equation \\(f(\vec{x})=\vec{b}\\) can be expressed as an implicit function \\(g\\) acting on \\(n-m\\) active variables (components of \\(\vec{x}\\)), yielding the remaining \\(m\\) components (passive variables). In particular, we may write
\\[g\begin{pmatrix}
x_{i_1}\\\\\
\vdots\\\\\
x_{i_{n-m}}\end{pmatrix}=\begin{pmatrix}x_{j_1}\\\\\
\vdots\\\\\
x_{j_m}\end{pmatrix},\\]
where \\(\{x_{j_1},...,x_{j_m}\}=\{x_1,...,x_n\}-\{x_{i_1},...,x_{i_{n-m}}\}\\). The regularity condition is an interesting one. I'm not sure I quite get it. When the derivative of \\(f\\) fails to be surjective, that means that the rank of the Jacobian matrix is not equal to \\(m\\). This means that at least one of the column vectors of the Jacobian can be written as a linear combination of the others. That is, one of the partial derivatives of \\(f\\) is a linear combination of some of the others.

This is a strange condition. The partial derivatives of \\(f\\) must be linearly independent for an implicit function to be guaranteed to exist. If I think really hard, I can come up with the following heuristic.

Suppose a partial derivative of \\(f\\) can be written as a linear combination of other partial derivatives of \\(f\\). This means that there are *two* directions one can move from \\(\vec{c}\\) in \\(U\\) so that the change in \\(f\\) is the same. One is along a standard basis vector, and the other is along some linear combination of other standard basis vectors. This leads to a problem. If there are two points in a small neighborhood of \\(\vec{c}\\) that have the same image through \\(f\\), there must be a small neighborhood of \\(f(\vec{c})\\) (by continuity) that has a point that is the image of more than one point in the domain. This immediately implies that a local inverse doesn't exist here. But apparently, a local implicit function doesn't exist here either.

Anyway, perhaps it's a lot more meaningful to think about what the implicit function allows us to do, which is to talk about a rudimentary definition of a manifold. To do this, first we define the *graph* of a function. I know, I know, we all know what a graph of a function looks like. But what *is* a graph?

**Definition:** Consider a function \\(g\colon\mathbb{R}^{k}\to\mathbb{R}^{n-k}\\). The *graph* of \\(g\\), denoted by \\(\Gamma(g)\\), is the set of points \\(\begin{pmatrix}\vec{x}\\\\ \vec{y}\end{pmatrix}\in\mathbb{R}^n\\) such that \\(f(\vec{x})=\vec{y}\\).

This makes a lot of sense, especially if you think about visualizable cases like \\(k=2\\) and \\(n=3\\). In this case, the graph of the function lives in \\(\mathbb{R}^3\\) and is, well, literally the graph of the function we are thinking about.

A \\(k\\)-*dimensional manifold* is then some set that locally resembles \\(\mathbb{R}^k\\).

Before we get more precise, let us think of an example. The saddle surface of a potato chip is a two-dimensional manifold since if we zoomed in on it, it looks like \\(\mathbb{R}^2\\). The union of the coordinate axes in \\(\mathbb{R}^2\\) is not a one-dimensional manifold, since at the origin, no matter how much we zoom, it does not look like \\(\mathbb{R}\\).

Oh, and it should be mentioned that most manifolds that we think about are actually *submanifolds* that are embedded in a higher-dimensional space. But for our purposes, we'll ignore this and call what we think of just *manifolds*.

Suppose that \\(\vec{b}\\) is a regular value of \\(f\colon\mathbb{R}^n\to\mathbb{R}^m\\). Then, consider the subset of the graph \\(\Gamma(f)\\) where the only value \\(f\\) is mapping to is \\(\vec{b}\\). Denote this subset as \\(f^{-1}(\vec{b})\\). In particular, \\(f^{-1}(\vec{b})\\) lives in \\(\mathbb{R}^{m+n}\\).

By the implicit function theorem, in a small neighborhood of any point in \\(f^{-1}(\vec{b})\\), the intersection of \\(f^{-1}(\vec{b})\\) and that neighborhood is the graph of some local implicit function \\(g\colon U\to\mathbb{R}^m\\), where \\(U\subset\mathbb{R}^{n-m}\\).

The idea is that \\(g\\) is an isomorphism between a subset of \\(\mathbb{R}^{n-m}\\) and a part of \\(f^{-1}(\vec{b})\\). So, for small sections, \\(f^{-1}(\vec{b})\\) is isomorphic to \\(\mathbb{R}^{n-m}\\). This is what we mean when we say "resembles". In our particular case, \\(f^{-1}(\vec{b})\\) is a \\((n-m)\\)-dimensional submanifold of \\(\mathbb{R}^{m+n}\\).

I'll eventually get around to learning the proof of the implicit function theorem. It's pretty messy, and involves Kantorovich's theorem and Lipschitz ratios, neither of which I am familiar with. Perhaps I'll start a blog series on my progress treading through those topics!