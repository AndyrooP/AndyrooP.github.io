---
layout: post
title: "Denseness of Rationals: Finitely generated subgroups are not necessarily discrete"
date: 2021-7-25 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
That the rationals are dense in the real numbers is a basic property that any student would learn in a first course in topology or real analysis. The standard proof uses the Archimedean property of the real numbers. Here, I outline a different way to prove that an irrational number can be approximated to arbitrary accuracy by rational numbers. This is, in some sense, the "hardest" case to prove, if we attempt to show that rational numbers and irrational numbers can both be approximated by rationals, separately.

The idea is that a finitely generated additive subgroup of \\(\mathbb{R}\\) need not be discrete. Let \\(x\\) be irrational and \\(p\\) rational. Consider the set of real numbers of the form \\(ax+bp\\) where \\(a,b\in\mathbb{Z}\\). Suppose there is a nontrivial solution to \\(ax+bp=0\\). Then, \\(x=-\frac{bp}{a}\in\mathbb{Q}\\), a contradiction. Hence, no integer multiple of \\(x\\) is equal to an integer multiple of \\(p\\).

If we let \\(p=1\\), we discover a consequence of this: if we move around a circle in steps by doing \\(x\\) rotations around the circle each step, we will never reach the same point more than once. Let \\(S\\) denote the subset of points of the circle that we will reach by performing these steps. Our reasoning shows that \\(S\\) is countably infinite. If we partition the circle into \\(N\\) equal arcs, where \\(N\\) is any integer, it follows from the pigeonhole principle that there exists an arc that contains infinitely many of the points on the circle we will reach by making such steps.

This means that for any arbitrarily small neighborhood size, one may find a point on the circle with a neighborhood of that size that has infinitely many points from \\(S\\). By rotating the starting point of our steps, we rotate the point on the circle that is guaranteed the existence of this neighborhood. So every​ point on the circle has infinitely many points from \\(S\\). That is, \\(S\\) is dense in the circle.

Let \\(p=q\\) where \\(q\\) is some fixed nonzero rational number. Since \\(S\\) is dense in the circle, and the integer multiples of \\(q\\) can be represented as points in the circle, we have that for any \\(\epsilon>0\\), we can find \\(m,n\in\mathbb{Z}\\) (with \\(n\neq0\\)) such that
\\[|mq+nx|<\epsilon\Longrightarrow\left|x+\frac{mq}{n}\right|<\frac{\epsilon}{|n|}\leq\epsilon.\\]
So \\(-\frac{mq}{n}\\) is a rational number that is within \\(\epsilon\\) of \\(x\\).