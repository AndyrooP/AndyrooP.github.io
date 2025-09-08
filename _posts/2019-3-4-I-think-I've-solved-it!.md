---
layout: post
title: "I think I've solved it!"
date: 2019-3-4 10:00:00
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Remember that little lemma from last time? The one that showed that \\(q\leq p\\)? Let us define a new sequence:
\\[p_n=\frac{a_n}{n}\\]
According to our lemma, \\(p_n\\) constitutes a decreasing sequence. Now, let us construct another sequence that bounds \\(p_n\\). In particular, I want the \\(n^{\textrm{th}}\\) term of this sequence to be less than or equal to \\(p_n\\). I noted that I could accomplish this by modifying \\(a_n\\) such that I rounded *down* each time, instead of merely to the nearest multiple of \\(n\\). Hence, I defined my new sequence as:
\\[b_1=p_1\\]
And then, each new \\(b_n\\) would be obtained by rounding *down* to the nearest \\(n\\) and then dividing by \\(n\\):
\\[b_{n+1}=\left\lfloor \frac{n}{n+1}b_n \right\rfloor\\]
I rewrote this recursive definition by splitting the floor into the difference of the actual ratio and the fractional part:
\\[b_{n+1}=\frac{n}{n+1}b_n-\left\\{\frac{n}{n+1}b_n\right\\}\\]
This rearranged to:
\\[\frac{n}{n+1}b_n-b_{n+1}=\left\\{\frac{n}{n+1}b_n\right\\}\\]
Now observe that the fractional part of any number is between \\(0\\) (inclusive) and \\(1\\) (exclusive). Hence:
\\[0\leq\frac{n}{n+1}b_n-b_{n+1}<1\\]
At this point, I observed that the first inequality in this chain could be rearranged to:
\\[b_{n+1}\leq\frac{n}{n+1}b_n\\]
So the sequence was decreasing! Next, I observed that since \\(b_1>0\\), then all \\(b_{n+1}=\left\lfloor \frac{n}{n+1}b_n \right\rfloor\\) must be at least \\(0\\). This implied that the sequence was bounded as well! Hence, \\(\lim_{n\rightarrow\infty}{b_n}\\) existed.

Since \\(p_n\\) is bounded below by \\(b_n\\) and is also decreasing, \\(\lim_{n\rightarrow\infty}{p_n}\\) existed as well, and all sequences of \\(a_n\\) must therefore converge to arithmetic sequences!

This was such a delightful problem! I do hope that my reasoning is correct. I have never quite proven something in this way before, but it makes perfect sense to me! Hooray!