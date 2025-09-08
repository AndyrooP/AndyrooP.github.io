---
layout: post
title: "The Classic..."
date: 2019-6-23 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

**Problem (IMO 1959):** Prove that for natural \\(n\\) the fraction \\(\frac{21n+4}{14n+3}\\) is irreducible.

*Solution*: Suppose to the contrary that the fraction is reducible. Then, there must exist a prime \\(p|21n+4\\) and \\(p|14n+3\\). In other words, \\(21n+4\equiv0\pmod p\\) and \\(14n+3\equiv0\pmod p\\). Adding these two congruences:
\\[7(5n+1)\equiv0\pmod p.\\]
Observe that \\(p\neq7\\), since \\(7\\) divides neither \\(21n+4\\) nor \\(14n+3\\). Hence:
\\[5n+1\equiv0\pmod p.\\]
Suppose \\(p=2\\). Then to satisfy this congruence, \\(n\\) must be odd. But then \\(21n+4\\) would be odd and \\(p=2\\) would not be able to divide it, contradiction. Hence \\(p\neq2\\) and it must instead be an odd prime.

Subtracting the two original congruences yields:
\\[7n+1\equiv0\pmod p.\\]
Now subtracting this congruence with the previous one, we obtain
\\[2n\equiv0\pmod p.\\]
Since \\(p\neq2\\), we must have
\\[n\equiv0\pmod p.\\]
But now, \\(21n+4\equiv4\pmod p\\), and \\(4\equiv 0\pmod p\\) if and only if \\(p=2\\), contradiction.

Hence there cannot be a prime that divides both \\(21n+4\\) and \\(14n+3\\) and the fraction \\(\frac{21n+4}{14n+3}\\) must be irreducible. \\(\square\\)

Edit: Yes, I know the result immediately follows from the Euclidean algorithm. For some reason, I could only remember the *extended* Euclidean algorithm when I was solving this problem.