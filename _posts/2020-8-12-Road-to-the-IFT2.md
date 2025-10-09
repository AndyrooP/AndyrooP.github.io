---
layout: post
title: "Road to the Implicit Function Theorem: Part 2 – Kantorovich's Theorem"
date: 2020-8-12 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
Now that we have the tools to do so, let us discuss Kantorovich's theorem.

Let \\(\vec{a}\_0\\) be a point in \\(\mathbb{R}^n\\), \\(U\\) an open neighborhood of \\(\vec{a}\_0\\) in \\(\mathbb{R}^n\\), and \\(f\colon U\to\mathbb{R}^n\\) a differentiable mapping, with its derivative \\([Df(\vec{a}\_0)]\\) invertible. Define
\\[\vec{h}\_0=-\[Df(\vec{a}\_0)\]^{-1}f(\vec{a}\_0),\ \vec{a}\_1=\vec{a}\_0+\vec{h}\_0,\ U\_1=B_{\|\vec{h}\_0\|}(\vec{a}\_1).\\]
If \\(\overline{U}_1\subset U\\) and the derivative \\([Df(\vec{x})]\\) satisfies a Lipschitz condition with Lipschitz ratio \\(M\\) for all points in \\(\overline{U}_1\\), and if the inequality
\\[|f(\vec{a}_0)|\left|[Df(\vec{a}_0)]^{-1}\right|^2M\leq\frac{1}{2}\\]
is satisfied, the equation \\(f(\vec{x})=\vec{0}\\) has a unique solution in the closed ball \\(\overline{U}_1\\), and Newton's method with initial guess \\(\vec{a}_0\\) converges to it.

What a mouthful, eh? To understand what's really being said here, we need to unpack the inequality. The inequality essentially encodes the three heuristic conditions that we discussed in the previous part.

* Our initial guess should already be close to being a root. So \\(\|f(\vec{a}_0)\|\\) should be small.
* The rate of change at our guess should be large in magnitude so that we have a greater chance of budging and moving towards the locus \\(f(\vec{x})=0\\). So \\(\left\|\[Df(\vec{a}_0)\]\right\|\\) should be large and \\(\left\|\[Df(\vec{a}_0)\]^{-1}\right\|^2\\) should be small.
* The derivative must not change much at our guess. Otherwise, while it may start out to be large in magnitude and satisfy the previous bullet point, it will quickly become small in magnitude as we move away from our guess. So \\(M\\) must be small.

Magically putting all of these together gives us the inequality in the statement of Kantorovich's theorem. The proof of existence works by proving four statements.

1. \\([Df(\vec{a}_1)]\\) is invertible, allowing us to define \\(\vec{h}_1=-[Df(\vec{a}_1)]f(\vec{a}_1)\\) for the next iteration of Newton's method,
2. \\(\|\vec{h}_1\|\leq\frac{\|\vec{h}_0\|}{2}\\),
3. \\(\|f(\vec{a}_1)\|\left\|\[Df(\vec{a}_1)\]^{-1}\right\|^2\leq\|f(\vec{a}_0)\|\left\|\[Df(\vec{a}_0)\]^{-1}\right\|^2\\),
4. \\(\|f(\vec{a}_1)\|\leq\frac{M}{2}\|\vec{h}_0\|^2\\).

If the first three statements are true, then we can continue Newton's method and the necessary hypothesis for Kantorovich is satisfied at each iteration. Furthermore, the second statement implies that the sequence \\(i\mapsto\vec{a}_i\\) converges (use the triangle inequality). Then, combining parts 2 (iteratively) and 4, we have the inequality
\\[\|f(\vec{a}\_i)\|\leq\frac{M}{2}\|\vec{h}\_{i-1}\|^2\leq\frac{M}{2^i}\|\vec{h}\_0\|^2,\\]
and by the squeeze theorem, we get the desired result as we take the limit \\(i\to\infty\\).

A hefty task, I know. The theorem was only proven in 1948! The proof of uniqueness proceeds by showing that if \\(\vec{y}\in U_1\\) is a root, then \\(\vec{y}\\) must be the limit of \\(i\mapsto a_i\\), which suffices due to the uniqueness of the limit.

As it turns out, this statement of the theorem can actually be strengthened, provided that we use a different type of norm of linear transformations in the inequalities of the theorem statement. Recall that we originally used the Frobenius norm. Now, we introduce the _operator norm_ of a linear transformation. For a linear transformation \\(A\colon\mathbb{R}^n\to\mathbb{R}^m\\), the operator norm is defined as
\\[||A||=\sup{|A\vec{x}|},\\]
where \\(\vec{x}\in\mathbb{R}^n\\) is of unit length. As it turns out, we can replace the Frobenius norm with the operator norm in the inequalities of Kantorovich's theorem, and the theorem remains true. The reason why this gives us a _stronger_ form of the theorem is that
\\[||A||\leq|A|,\\]
for any linear transformation. That is, the operator norm of a linear transformation is always at most the Frobenius norm of the linear transformation. This means that the inequalities of Kantorovich's theorem are easier to satisfy if we are allowed to use the operator norm instead.

So in fact, we are not groping around in the dark when we use Newton's method. There are conditions where Newton's method is guaranteed to converge. Note that while Kantorovich gives a sufficient condition for convergence, it is _not_ necessary. Now we can be a bit more justified when we use Newton's method in proving the implicit and inverse function theorems.