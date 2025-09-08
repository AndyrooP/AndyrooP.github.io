---
layout: post
title: "What goes around comes around"
date: 2019-8-10 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Back in my (early) wannabe days, in the summer between sophomore and junior year, I was studying single-variable calculus. From the AoPS book, I found this extra sidenote.

Consider a positively oriented closed simple curve (a curve that is closed, non-self intersecting, and traced such that region enclosed by the curve is always on the left) parameterized by \\((x(t),y(t))\\) from \\(t_0\\) to \\(t_1\\). Then, the area of the enclosed region is given by:
\\[\frac{1}{2}\int_{t_0}^{t_1}{x(t)y'(t)-x'(t)y(t)\textrm{ d}t}.\\]
Back then, I could barely understand the statement, and once I did, I had no clue as to how it would be true. The sidenote said that it was a special case of *Green's Theorem* from vector calculus.

Two years later, I can finally say that I know where this comes from.

Green's theorem states that for a positively oriented closed simple curve \\(C\\) enclosing a region \\(R\\), and a vector field \\(\mathbf{F}\\),
\\[\oint_{C}{\mathbf{F}\cdot\textrm{d}\mathbf{r}}=\iint_{R}{\nabla\times\mathbf{F}\textrm{ d}A},\\]
where \\(\nabla\times\mathbf{F}\\) is the 2D curl (I know, it's a 3D thing so I'm abusing the notation a little). This is a cool result. For instance, it immediately establishes all the stuff about path-independence of line integrals over conservative fields which have to be curl-free and blah, blah, blah.

If \\(\nabla\times\mathbf{F}=1\\), then the RHS evaluates to the area of \\(R\\). So we want a vector field, \\(\mathbf{F}=\langle M,N\rangle\\), such that \\(\frac{\partial N}{\partial x}-\frac{\partial M}{\partial y}=1\\). Perhaps the simplest \\(\mathbf{F}\\) satisfying this is \\(\mathbf{F}=\left\langle -\frac{y}{2},\frac{x}{2}\right\rangle\\). Then by Green's theorem, we have
\\[\begin{split}
A&=\oint_{C}{-\frac{y}{2}\textrm{ d}x+\frac{x}{2}\textrm{ d}y}\\
&=\frac{1}{2}\oint_{C}{\left(x\frac{\textrm{d}y}{\textrm{d}t}-y\frac{\textrm{d}x}{\textrm{d}t}\right)\textrm{d}t}\\
&=\frac{1}{2}\int_{t_0}^{t_1}{x(t)y'(t)-x'(t)y(t)\textrm{ d}t},
\end{split}\\]
as desired. \\(\square\\)

​Cool beans.