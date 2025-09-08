---
layout: post
title: "Current Progress on the Rounding Sequence"
date: 2019-3-3 10:00:00
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Here is my current progress on the problem I described in my previous post.

​First, I observed that \\(|a_{n+1}-a_n|\\) is maximized when \\(a_n\\) is equidistant (or as close as possible to being equidistant) to consecutive multiples of \\(n+1\\). Hence:
\\[|a_{n+1}-a_n|\leq\left\lfloor \frac{n+1}{2} \right\rfloor\\]
Next, I considered a general term \\(a_n=np\\) and \\(a_{n+1}=(n+1)q\\) (where of course \\(p,q\in\mathbb{Z}\\). WLOG, I let \\(a_{n+1}>a_n\\). This was the case of interest anyway. Under these assumptions, I had:
\\[np+R=(n+1)q\Rightarrow q=\frac{np+R}{n+1}\\]
I set this to be less than or equal to \\(p\\). At the time, it just assumed this via heuristics. It wasn't until later until I was able to actually prove it.

**Lemma:** Let \\((n+1)q>np\\) be the closest multiple of \\(n+1\\) to \\(np\\). Then \\(p\geq q\\)

**Proof:** Suppose that to the contrary, \\((n+1)r>np\\) was the closest multiple of \\(n+1\\) to \\(np\\), where \\(r>p\\). Then, the difference between the two numbers is:
\\[nr+r-np=n(r-p)+r\\]
Observe that \\(r-p\geq1\Rightarrow n(r-p)\geq n\\) and \\(r>1\\) (by implicit assumption). Adding these two inequalities yields:
\\[n(r-p)+r>n+1\\]
The maximum possible distance between a multiple of \\(n\\) and the closest larger multiple of \\(n+1\\) is \\(n+1\\), and this occurs when the aforementioned multiple of \\(n\\) is also a multiple of \\(n+1\\). However, we have shown that the distance between \\((n+1)r\\) and \\(np\\) is greater than \\(n+1\\), contradicting our initial assumption that \\((n+1)r\\) was the closest multiple of \\(n+1\\) that was larger than \\(np\\). Hence, \\(\exists q\leq p\\) such that \\((n+1)q\\) is the closest larger multiple of \\(n+1\\) to \\(np\\). \\(\square\\)

Ok that's cool. So that means that we can safely set our expression for \\(q\\) to be lesser than or equal to \\(p\\):
\\[\frac{np+R}{n+1}\leq p\\]
We can rearrange this inequality to obtain:
\\[p\geq R\\]
The equality condition is more interesting. When \\(p=R\\), we must also have \\(p=q\\), and the sequence becomes arithmetic (\\(n=k\\)). This can more easily be obtained by noting that \\(R=(n+1)q-np\\). But when does \\(p=R\\)? Here is what I did know:
\\[0\leq R\leq\left\lfloor \frac{n+1}{2} \right\rfloor\\]
\\(0\\) wasn't particularly interesting... but what about the upper bound? Letting \\(R\\) equal its upper bound seemed to match experimental results of my program for \\(a_k\\)! So I strongly suspect that:
\\[a_k=k\left\lfloor \frac{k+1}{2} \right\rfloor\\]
The question is, does this \\(a_k\\) always occur? How do I go about showing that it does? I have shown that \\(q\leq p\\), but how do I show that \\(q=p\\) will eventually occur?