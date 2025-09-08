---
layout: post
title: "Derangements"
date: 2019-8-13 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Let's solve a cool problem.

Suppose there is an \\(n\\) person committee. Let an arrangement of this committee be a *derangement* if none of the committee members are sitting where they are supposed to be sitting.

Let \\(P(n)\\) be the probability that a randomly chosen arrangement of the \\(n\\) person committee is a derangement. What is \\(\lim_{n\rightarrow\infty}{P(n)}\\)? That is, what does this probability approach as the number of members grows arbitrarily large?

First, let us define some notation. Let \\(D_n\\) be the number of derangements of an \\(n\\) person committee. How can we count \\(D_n\\)?

There are \\(n!\\) possible arrangements. Perhaps we can use complementary counting by finding the total number of arrangements where at least one member is sitting in his or her assigned seat, and then subtract that number from \\(n!\\).

It turns out that it is pretty much impossible to count how many different ways we can have an arrangement with exactly \\(1\leq k\leq n\\) members in their correct seat. Try it for yourself and see what problems you run into. There is no *simple* algorithm to derange a set. Note that I say *simple*. It is certainly possible to construct an algorithm based on swapping elements that are in the correct spots. Good luck keeping track of that for counting purposes.

Instead, we take a step back and think. We only need the *sum* of the number of arrangements with exactly \\(k\\) members in their correct seat from \\(k=1\\) to \\(k=n\\). Observe that while it is difficult to count the number of arrangements with *exactly* \\(k\\) correct seatings, it is much easier to count the number of arrangements with *at least* \\(k\\) correct seatings. We can then use the principle of inclusion-exclusion to deduce the sum of the number of arrangements with exactly \\(k\\) correctly seated members without counting a single such case!

So we calculate the number of possible arrangements where at least \\(k\\) people are sitting in his or her own assigned seat. There are \\(\binom{n}{k}\\) ways of choosing the number of ways to choose which people are guaranteed to sit in their correct seats. This leaves \\((n-k)!\\) ways to arrange the remaining people however we wish. It is totally possible that while arranging the these remaining people, someone gets seated where they are supposed to, hence why \\(\binom{n}{k}(n-k)!=\frac{n!}{k!}\\) is only the number of arrangements where *at least* \\(k\\) people are seated correctly.

By the principle of inclusion-exclusion, the alternating sum of these must be the desired value. Hence,
\\[\begin{split}
D_n&=n!-\left[\frac{n!}{1!}-\frac{n!}{2!}+...+(-1)^{n+1}\frac{n!}{n!}\right]\\
&=n!\sum_{k=0}^{n}{\frac{(-1)^{k}}{k!}}.
\end{split}\\]

Since the total number of arrangements is \\(n!\\), we can easily calculate the probability:
\\[P(n)=\frac{D_n}{n!}=\sum_{k=0}^{n}{\frac{(-1)^{k}}{k!}}.\\]
Taking the limit,
\\[\lim_{n\rightarrow\infty}{P(n)}=\sum_{k=0}^{\infty}{\frac{(-1)^{k}}{k!}}.\\]
But now the RHS is the Taylor series of \\(e^x\\) evaluated at \\(x=-1\\)! Hence our requested limit is simply \\(\boxed{\frac{1}{e}}\\). This is approximately 36.8%.

The function \\(D_n\\) enjoys a number of cool properties. One of them is:
\\[\sum_{k=0}^{n}{\binom{n}{k}D_{n-k}}=n!.\\]
See if you can find a combinatorial proof of this.

*Hint*: The construction is similar in spirit to the one we used to find the sum of the number of arrangements with exactly \\(k\\) correctly seated members.