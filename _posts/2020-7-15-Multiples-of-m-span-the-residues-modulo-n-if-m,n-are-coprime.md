---
layout: post
title: "Multiples of $m$ span the residues modulo $n$ if $m,n$ are coprime"
date: 2020-7-15 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
Consider all of the residues modulo 20. Given any one of those residues, can you always find a multiple of 7 that leaves that residue modulo 20?

The solution to this is fairly simple. In fact, the *simple* solution to this did not occur to me until I proved a generalization of the statement. Regardless, I will show that solution here first for demonstration purposes.

In the case of 7, it is immediately apparent that \\(21\equiv1\pmod{20}\\). So if we desire to produce the residue \\(k\\), just take \\(3k\cdot 7\\).

There it is. Simple, right? In fact, not only is it simple, but it's a bit cheap. It doesn't really tell us what's going on under the hood. We just conveniently found a multiple of 7 that was congruent to 1 modulo 20. So let's walk away from the specificity of the numbers 7 and 20 and instead pose the following problem.

Let \\(m,n\in\mathbb{N}\\) be coprime, with \\(m<n\\). Given any residue modulo \\(n\\), can one always find a multiple of \\(m\\) that leaves that residue modulo \\(n\\)?

Obviously, if we can show that there exists a multiple of \\(m\\) congruent to 1 modulo \\(n\\), we're done. But it wasn't obvious to me how to proceed with this idea that worked very quickly for 7 and 20, for general \\(m\\) and \\(n\\). And anyway, the idea with 21 only came to me after I had already solved this problem.

Instead, the first thing I saw here is that we only need to work with multiples of \\(m\\) up to \\(mn\\). This is because \\(m(n+r)\equiv mr\pmod{n}\\). This is actually the first solution I presented to the original problem with 7 and 20. Just check all of the multiples of 7 up to 140. Of course this isn't as efficient as the observation of \\(3k\cdot7\\).

So let \\(A=\{m,2m,\ldots,mn\}\\). From this set, the first thing I observed was that the first half of the set cancelled with partners reflected across the middle into the last half of the set, modulo \\(n\\). For instance, \\(m+m(n-1)\equiv0\pmod{n}\\). But this still didn't answer the question. Because there was no indication that when we look through the pairings, every residue was covered. This made me wonder how much room I had for overlapping residues.

It turns out, conveniently, that the answer to that question is "none". Observe that the set of residues modulo \\(n\\) is \\(B=\{0,1,\ldots,n-1\}\\). More importantly, \\(\|A\|=\|B\|=n\\). Now we're going somewhere! By the pigeonhole principle, the answer to our question is "yes" if and only if each multiple in \\(A\\) gives a unique residue modulo \\(n\\).

Obviously \\(mn\\) takes care of the residue 0. Since \\(m\\) and \\(n\\) are coprime, no other element of \\(A\\) leaves that residue of 0. So now, excluding \\(mn\\), let us take two elements of \\(A\\), say \\(km\\) and \\(jm\\). Suppose, to the contrary, that they do leave the same residue modulo \\(n\\). Then \\(km\equiv jm\pmod{n}\\).

Since \\(m\\) and \\(n\\) are coprime, we have \\(\gcd{(m,n)}=1\\) so we can divide the congruence by \\(m\\) to obtain \\(k\equiv j\pmod{n}\\). But this is a contradiction! Because \\(0<k<j<n\\) or \\(0<j<k<n\\).

So the answer to our question is "yes".