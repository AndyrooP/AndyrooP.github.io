---
layout: post
title: "The Summer is Here!"
date: 2020-6-25 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
The summer has arrived and I'm back in Florida! Let us begin with a cutie.

**Problem:** Consider the number
\\[k(n)=1\underbrace{4...4}_{\text{$n$ digit $4$'s}}.\\]
For what values \\(n\\) is \\(k(n)\\) a perfect square?

*Solution*: \\(k(0)\\) is obviously a perfect square and \\(k(1)\\) is obviously not. For \\(n>1\\), we have that \\(k(n)\\) is even, since it ends with the digit 4. Any even square is divisible by 4. By long division, we find that for \\(n>1\\),
\\[\frac{k(n)}{4}=36\underbrace{1...1}_{\text{$n-2$ digit $1$'s}}.\\]
So it suffices to find the \\(n\\) for which this number is a square. Observe that squares are congruent to either 0 or 1 modulo 4 (if you've stuck around here for some time, you'd notice that we LOVE taking squares modulo 4). But, by long division, we see that \\(\frac{k(n)}{4}\\) is congruent to 3 modulo 4 whenever \\(n>3\\). So, we need to only check \\(n=2\\) and \\(n=3\\).

Indeed, \\(144=12^2\\) and \\(1444=38^2\\). So \\(k(n)\\) is square precisely when \\(n\in\\{0,2,3\\}\\). \\(\square\\)

​I have a few ideas about what I plan on doing next here. I want to talk about Lebesgue integration. The theory of Riemann integration that we thoroughly developed in MATH 31CH is a powerful conceptual tool, but it has several weaknesses. For example, the Riemann integral is not well-defined over \\(\mathbb{R}^n\\) for functions with unbounded supports.

The Lebesgue integral allows us to integrate over unbounded supports. This is just one of the advantages it gives. The Lebesgue integral is also considerably more well-behaved under limits, and we'll see that this gives rise to the *dominated convergence theorem* (DCT), regarding the interchangeability of integrals and limits (which is something that many of us take for granted \*cough\*MAO heuristics\*cough\*). This can be extended even further to talk about the interchangeability of differentiation and integration when they are composed on a function. Yes, that's right. The theory of Lebesgue integration is what forms the rigorous underpinnings of Feynman's trick!

I will be going through these topics soon, in a main page post. I like this idea, because it sort of pulls together a bunch of stuff that I've seen or worked on for the past few weeks (my final project in MATH 31CH was on Lebesgue integration and Feynman's trick, which a homework problem in physics happened to use, and I also recently stumbled into a problem where one needs to apply DCT). I don't expect that I'll be proving certain things, such as DCT itself and the existence of the Lebesgue integral, because the proofs are quite technical, and honestly you'd be better off reading a textbook if you're looking for those. Instead, I will try my best to show the motivation behind the Lebesgue integral and its utility in approaching problems that are pretty much intractable with Riemann's theory.

​I should have more time to work on this now. After all, UCSD decided to cancel one of my summer classes (MATH 120A)....