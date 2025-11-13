---
layout: post
title: "Nontrivial Cohomology"
date: 2024-5-19 12:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Let \\(S^1\\) be the unit circle as a 1-dimensional manifold. Let \\(\omega\\) be the 1-form on \\(S^1\\) defined by
\\[\omega=\frac{x+y}{x^2+y^2}\, \mathrm{d}x+\frac{y-x}{x^2+y^2}\, \mathrm{d}y,\\]
where \\(x\\) and \\(y\\) are the standard coordinates on \\(S^1\\). A simple calculation shows that this differential form is closed. A calculation also shows that when \\(S^1\\) is given the counterclockwise orientation, we have that \\(\int\_{S^1}{\omega}=\int\_{0}^{2\pi}{-1\, \mathrm{d}\theta}=-2\pi\\).

However, \\(\omega\\) clearly extends to a closed 1-form \\(\Omega\\) on the manifold \\(M:=D^2\setminus\\{(0,0)\\}\\), where \\(D^2\\) is the closed unit disk in \\(\mathbb{R}^2\\). Note that \\(\partial M=S^1\\). Stokes' theorem then suggests that
\\[\int\_{S^1}{\omega}=\int\_{M}{\mathrm{d}\Omega}=\int\_{M}{0}=0.\\]
What is the discrepancy?

The issue is that the precise statement of Stokes' theorem calls for the support of the \\(\Omega\\) to be compact. Since our manifold \\(M\\) has a "hole" at the origin. Hence, Stokes' theorem does not apply in this case. Of course, if we replace \\(M\\) with \\(D^2\\), then if \\(\omega\\) extends to a closed 1-form on \\(D^2\\), the support of this extension would indeed be compact so Stokes' theorem would tell us that \\(\int\_{S^1}{\omega}=0\\). Hence, it cannot be the case that \\(\omega\\) extends to a closed 1-form on \\(D^2\\).