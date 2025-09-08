---
layout: post
title: "The Equation of Continuity"
date: 2019-12-19 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
Continuing on an MIT pset, we have the following equation for fluid flow. Let \\(\mathbf{F}(x,y,t)=\rho (x,y,t)\mathbf{v}(x,y,t)\\), where \\(\rho\\) is density and \\(\mathbf{v}\\) is velocity. Then,
\\[\frac{\partial\rho}{\partial t}+\nabla\cdot\mathbf{F}=0.\\]
This is the so-called *equation of continuity*. As it turns out, it is simply equivalent to the conservation of mass. We can see this by integrating the equation over some region \\(R\\). We obtain
\\[\iint_{R}{\frac{\partial\rho}{\partial t}\textrm{ d}A}=-\iint_{R}{\nabla\cdot\mathbf{F}\textrm{ d}A}.\\]
But now, using Green's theorem in normal form, the RHS becomes a line integral over \\(C\\), which is the positively-oriented boundary of \\(R\\):
\\[\iint_{R}{\frac{\partial\rho}{\partial t}\textrm{ d}A}=-\oint_{C}{M\textrm{ d}y-N\textrm{ d}x},\\]
where \\(M\\) and \\(N\\) are the \\(x\\) and \\(y\\) components of \\(\mathbf{F}\\), respectively. Observe that the RHS is now the negative of the fluid flux through \\(C\\). That is, the change in pressure over a region is equal to the negative of the flux through the boundary of that region. Obviously. If mass wants to leave a region, it must pass through the boundary of that region. It cannot simply "vanish". Mass is conserved.

In a previous blog post, we talked about the convective derivative, and how it is used in defining incompressible flow. In particular, a flow is incompressible when the convective derivative of the pressure is zero. We can combine this with the equation of continuity to find another necessary and sufficient condition for flow incompressibility. We have
\\[\begin{split}
\frac{D\rho}{Dt}&=\frac{\partial\rho}{\partial t}+\mathbf{v}\cdot\nabla\rho\\
&=0.
\end{split}\\]
But by rearranging the product rule, we have \\(\mathbf{v}\cdot\nabla\rho=\nabla\cdot(\rho\mathbf{v})-\rho\nabla\cdot\mathbf{v}\\). So our convective derivative becomes
\\[\frac{\partial\rho}{\partial t}+\nabla\cdot(\rho\mathbf{v})-\rho(\nabla\cdot\mathbf{v})=0.\\]
The first two terms sum to zero by the equation of continuity, which leaves us with \\(\boxed{\nabla\cdot\mathbf{v}=0}\\). Flow is incompressible only when the divergence of the velocity is zero.