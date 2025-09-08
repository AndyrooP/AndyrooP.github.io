---
layout: post
title: "I should be doing history homework but..."
date: 2019-4-4 10:00:00
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Here's what I *do* know.

For brevity, let \\(K=c+b\\).

Let \\(u=\rho(x)\\) and \\(\textrm{d}v=K-x\textrm{ d}x\\). Then, integrating by parts:
\\[\int{(K-x)\rho(x)\textrm{ d}x}=\rho(x)\left(Kx-\frac{1}{2}x^2\right)-\int{\left(Kx-\frac{1}{2}x^2\right)\rho'(x)\textrm{ d}x}\\]
We continue integrating by parts, letting the polynomial in each new integrand be \\(\frac{\textrm{d}v}{\textrm{d}x}\\), and the derivatives of \\(\rho(x)\\) be \\(u\\). This then yields:
\\[\int{(K-x)\rho(x)\textrm{ d}x}=\sum_{n=0}^{\infty}{(-1)^n\rho^{(n)}(x)\left(\frac{Kx^{n+1}}{(n+1)!}-\frac{x^{n+2}}{(n+2)!}\right)}\\]
Ok Andrew, cool. Now what? Ah, simply observe.

Our desired integral is the improper integral evaluated from \\(c\\) to \\(\infty\\). This means that the limit of the antiderivative (above) as \\(x\\) approaches \\(\infty\\) must converge! In other words:
\\[\lim_{x\rightarrow\infty}{\sum_{n=0}^{\infty}{(-1)^n\rho^{(n)}(x)\left(\frac{Kx^{n+1}}{(n+1)!}-\frac{x^{n+2}}{(n+2)!}\right)}}\\]
Must converge! For this to occur, every single term must converge! But observe that the polynomials in each term of the summation tend to \\(\infty\\), hence for convergence to occur, every derivative of \\(\rho(x)\\), along with \\(\rho(x)\\) itself, must tend to \\(0\\) (this follows plainly from L'Hôpital's rule). In other words, we have derived:
\\[\lim_{x\rightarrow\infty}{\rho^{(n)}(x)}=0\textrm{ }\forall n\in\mathbb{N}_0\\]
This in and of itself hints at possible functions. For instance, an exponential decay function, or something of the form \\(Ax^n\\) for some \\(n<0\\). Ok sure, we can substitute these functions into our original integral equation and find that *one of them actually works*, but I want a little more insight. And rigor. And what sort of lame solution is that? Deriving one property and guessing and checking? Ew.

The next thing I will use is the Leibniz integral rule. That is:
\\[\frac{\textrm{d}}{\textrm{d}x}\left(\int_{a(x)}^{b(x)}{f(x,t)\textrm{ d}t}\right)=f(x,b(x))\cdot\frac{\textrm{d}}{\textrm{d}x}b(x)-f(x,a(x))\cdot\frac{\textrm{d}}{\textrm{d}x}a(x)+\int_{a(x)}^{b(x)}{\frac{\partial}{\partial x}f(x,t)\textrm{ d}t}\\]
While this looks complicated, it just follows from the Fundamental Theorem of Calculus. And while I'd love to continue this post with the application of this rule, I should probably do my history for once. The next post will include this, and discussion of uniform continuity, and uniform and pointwise convergence.

​Stay tuned.