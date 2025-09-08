---
layout: post
title: "QM-AM Inequality"
date: 2020-5-21 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
The AM-GM inequality is a well-known result, and often a pretty nifty tool. Less well-known is the QM-AM inequality.  These two inequalities make up the more general mean-inequality chain. The quadratic mean (QM), sometimes called root-mean-square (RMS), is defined by
\\[\sqrt{\frac{x_1^2+...+x_n^2}{n}}.\\]
The QM-AM inequality then states
\\[\sqrt{\frac{x_1^2+...+x_n^2}{n}}\geq\frac{x_1+...+x_n}{n}.\\]

There are two nice ways to prove QM-AM. The first, which I will get out of the way, is by Cauchy-Schwarz. That inequality implies that
\\[n(x_1^2+...+x_n^2)=(1^2+...+1^2)(x_1^2+...+x_n^2)\geq(x_1+...+x_n)^2.\\]
Rearranging this yields
\\[\frac{x_1^2+...+x_n^2}{n}\geq\left(\frac{x_1+...+x_n}{n}\right)^2.\\]
Both sides are clearly nonnegative, so we can take the square root to obtain the result:
\\[\sqrt{\frac{x_1^2+...+x_n^2}{n}}\geq\frac{x_1+...+x_n}{n}.\\]
Cauchy-Schwarz also implies that the equality condition is precisely when the \\(x_i\\) are all equal.

This is clean, but it is pretty opaque. Mostly because Cauchy-Schwarz is not very intuitive (beyond the vector dot product geometric interpretation, do you really have a *feel* for why the numbers themselves must satisfy Cauchy-Schwarz?). Lucky for us, there is another, arguably more natural, way to derive QM-AM.

Suppose I gave you a list of four numbers at McDonald's. For each number, you are allowed to select one of the four types of chicken nuggets box that number of times (and you can only select each box type twice). For instance, if the set I gave you was \\(\{2,3,5,8\}\\). You select a number, for instance 5, and then select a box type (out of 4-piece, 6-piece, 10-piece, and 20-piece) for instance 10-piece, and buy five 10-pieces to get 50 chicken nuggets. How would you maximize the number of chicken nuggets you get? This is pretty obvious. The greedy algorithm is optimal. We pair the highest box numbers with the highest purchase numbers.

This gives rise to what is called the *rearrangement inequality*. If \\(a_i\leq a_j\\) and \\(b_i\leq b_j\\) iff \\(i\leq j\\), then we have that \\(\sum_{i=1}^{n}{a_ib_i}\\) is the maximal dot product of vectors with components \\(a_i\\) with vectors with components \\(b_i\\). In other words,
\\[\sum_{i=1}^{n}{a_ib_i}\geq\sum_{k=1}^{n}{a_kb_{\sigma(k)}},\\]
where \\(\sigma\\) is a permutation on \\(\{1,...,n\}\\). There is nothing complicated going on here. Just a super intuitive application of the greedy algorithm. Any third-grader can follow that.

​Now, it follows that
\\[a_1b_1+...+a_nb_n\geq a_1b_1+...+a_nb_n\\]
\\[a_1b_1+...+a_nb_n\geq a_1b_2+...+a_nb_1\\]
\\[\vdots\\]
\\[a_1b_1+...+a_nb_n\geq a_1b_{n-1}+...+a_nb_{n-2},\\]
where in each line we cycle through the order of \\(b_i\\). Now, observe what happens when we add all \\(n\\) of the inequalities together. We obtain:
\\[n\sum_{i=1}^{n}{a_ib_i}\geq\left(\sum_{k=1}^{n}{a_k}\right)\left(\sum_{j=1}^{n}{b_j}\right).\\]
Perhaps you see where this is going now. Suppose that \\(a_i=b_i=x_i\\). Then
\\[n(x_1^2+...+x_n^2)\geq(x_1+...+x_n)^2.\\]
Now, the rest of the proof follows as before with Cauchy-Schwarz.

A practical application of QM-AM is that it immediately establishes that the RMS speed is greater than the average speed of molecules in a gas. This avoids the use of the Maxwell-Boltzmann distribution. Deriving RMS speed can be (and is traditionally) done without Maxwell-Boltzmann, but doing it with Maxwell-Boltzmann is fun because it presents an interesting application of Feynman's trick. Perhaps I'll make a main page post about that.