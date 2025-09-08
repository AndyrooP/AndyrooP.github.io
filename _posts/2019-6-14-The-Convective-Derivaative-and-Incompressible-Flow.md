---
layout: post
title: "The Convective Derivative and Incompressible Flow"
date: 2019-6-14 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Here are two problems in a pset from MIT 18.02 (multivariable calculus).

**Problem 2:** Let \\(f(x,y,z,t)\\) be a smooth function, and let \\(\nabla f=\left<f_x,f_y,f_z\right>\\)​ be the gradient in *space* variables only. Let \\(\mathbf{r}=\mathbf{r}(t)=\left<x(t),y(t),z(t)\right>\\) be a smooth curve, and \\(\mathbf{v}=\mathbf{r}'(t)\\); and suppose we use the notation \\(\frac{\textrm{D}f}{\textrm{D}t}=\frac{\textrm{d}}{\textrm{d}t}f(\mathbf{r}(t),t)\\).

Use the Chain Rule to show that \\(\frac{\textrm{D}f}{\textrm{D}t}=\frac{\partial f}{\partial t}+\mathbf{v}\cdot\nabla f\\).

**Solution:** We have:
\\[f(\mathbf{r}(t),t)=f(x(t),y(t),z(t),t)\\]
By the Chain Rule:
\\[\frac{\textrm{d}}{\textrm{d}t}f(x(t),y(t),z(t),t)=\frac{\partial f}{\partial x}\frac{\textrm{d}x}{\textrm{d}t}+\frac{\partial f}{\partial y}\frac{\textrm{d}y}{\textrm{d}t}+\frac{\partial f}{\partial z}\frac{\textrm{d}z}{\textrm{d}t}+\frac{\partial f}{\partial t}\\]
Which becomes:
\\[\frac{\textrm{d}}{\textrm{d}t}f(x(t),y(t),z(t),t)=\frac{\partial f}{\partial t}+\left<\frac{\textrm{d}x}{\textrm{d}t},\frac{\textrm{d}y}{\textrm{d}t},\frac{\textrm{d}z}{\textrm{d}t}\right>\cdot\left<\frac{\partial f}{\partial x},\frac{\partial f}{\partial y},\frac{\partial f}{\partial z}\right>\\]
Which is:
\\[\frac{\partial f}{\partial t}+\mathbf{v}\cdot\nabla f\\]
As desired. \\(\square\\)

This function, \\(\frac{\textrm{D}f}{\textrm{D}t}\\), is called the *convective derivative* or the *material derivative*. In fact, there are <a href="https://en.wikipedia.org/wiki/Material_derivative#Names" target="_blank">quite a few names</a> for this. It is important to realize that \\(\mathbf{r}\\) defines a *path* or *trajectory* through space. The function \\(f\\) then describes something that is changing along a trajectory with time. The next problem makes this clear, letting \\(f=\rho\\), the density of a fluid.

When \\(\rho\\) is constant in \\(t\\), the flow is termed *steady*. Unsteady flow, as one can imagine by this definition, must be enormously complicated, and it includes phenomena such as turbulence. In the case of steady flow, each trajectory is called a *streamline*.

A fluid flow is called *incompressible* if the convective derivative of \\(\rho\\) is zero. In steady flow, this means that there is no pressure change along a streamline (which makes sense!).

**Problem 3a:** Suppose that the density function depends only on *time* \\(t\\) but is constant in the space variables \\((x,y,z)\\), that is, \\(\rho=\rho(t)\\). Then show that the flow is incompressible if and only if the density \\(\rho(t)\\) is constant in all the variables \\((x,y,z,t)\\) (in other words, the flow must be steady).

**Solution:** We want:
\\[\frac{\partial \rho}{\partial t}+\mathbf{v}\cdot\nabla\rho=0\\]
But since \\(\rho\\) does not depend on spatial variables, \\(\nabla\rho=0\\) and \\(\frac{\partial \rho}{\partial t}=\frac{\textrm{d}\rho}{\textrm{d}t}\\). Hence:
\\[\frac{\textrm{d}\rho}{\textrm{d}t}=0\\]
Integrating both sides WRT \\(t\\):
\\[\int{\frac{\textrm{d}\rho}{\textrm{d}t}\textrm{ d}t}=\rho(t)=C\\]
Hence, the flow is steady. \\(\square\\)

**Problem 3b:** Next suppose instead that the density depends only on the *space* variables \\((x,y,z)\\) but not (explicitly) on \\(t\\), so that \\(\rho=\rho(x,y,z)\\). An incompressible flow in this case is called *stratified*. Use the result of problem 2 to give the condition on \\(\rho\\) and \\(\mathbf{v}\\) for stratified flow.

**Solution:** In this case:
\\[\mathbf{v}\cdot\nabla\rho=0\\]
So the velocity is always orthogonal to direction in which \\(\rho\\) changes the most. But recall that \\(\nabla\rho\\) is always orthogonal to the contour surfaces of \\(\rho\\). It follows that the velocity must always be parallel, and hence tangential to, surfaces of equal density. \\(\square\\)