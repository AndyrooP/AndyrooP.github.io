---
layout: post
title: "Peak Unproductivity"
date: 2019-10-28 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
My linear class is weird.

Consider two continuous functions \\(f,g\colon [0,1]\to\mathbb{R}\\). Prove that
\\[\left|\int_{0}^{1}{f(x)g(x)\textrm{ d}x}\right|\leq\sqrt{\int_{0}^{1}{f(x)^2\textrm{ d}x}}\sqrt{\int_{0}^{1}{g(x)^2\textrm{ d}x}}.\\]
This problem is pretty trivial. Simply apply Cauchy-Schwarz to the Riemann sum approximation of the LHS and take the limit as \\(n\rightarrow\infty\\). This was a starred (challenge) problem in my linear homework following the week where we discussed Cauchy-Schwarz. Strange.

Anyway, I've encountered a lot of cute problems lately. Among these is the following.

**Problem (HMMT):** 10 students take a test. Each problem is solved by precisely 7 people and nine of the students solve exactly 4 of the problems. How many problems does the 10th student solve?

*Solution*: Let the number of problems on the test be \\(P\\). Consider a set of \\(P\\) bins, with each corresponding to a particular problem, and a set of 10 bins, with each corresponding to a particular student. For every student that solves a certain problem, we place a stone in that problem's bin and for every problem that a student solves, we place a stone in that student's bin. Note that if we place a stone in a problem's bin, we must also place a stone in a student's bin. That is, there exists a bijection between the stones in the problem bins and the student bins.

The total number of stones in the problem bins is given to be \\(7P\\) and the total number of stones in the student bins is \\(x+4\cdot9\\), where \\(x\\) is the number of problems that the 10th person solves. Hence,
\\[x=7P-36.\\]
Since \\(x\geq0\\), we must have \\(P\geq6\\). Furthermore, since the 10th person cannot solve more problems than are on the test, we have \\(x=7P-36<P\\), which means \\(P\leq6\\). Therefore, \\(P=6\\) and \\(x=\boxed{6}\\).