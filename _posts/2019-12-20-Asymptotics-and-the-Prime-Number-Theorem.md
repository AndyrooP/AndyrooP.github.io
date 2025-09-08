---
layout: post
title: "Asymptotics and the Prime Number Theorem"
date: 2019-12-20 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
Suppose that the \\(n\\)th prime number is given by \\(p_n\\) and the number of primes that do not exceed \\(n\\) is \\(\pi(n)\\). Let two functions \\(f\\) and \\(g\\) be asymptotic to each other, denoted by \\(f\sim g\\), iff \\(\lim_{x\rightarrow\infty}{\frac{f(x)}{g(x)}}=1\\). The prime number theorem states
\\[\pi(x)\sim \frac{x}{\log{x}}.\\]
This statement happens to be equivalent to \\(p_n\sim x\log{x}\\). I will show this equivalence, using the argument made in *An Introduction to the Theory of Numbers*, though with much of the gaps and leaps in reasoning filled in by myself.

The first thing to note is that \\(p_n\\) and \\(\pi(n)\\) are inverse functions. That is, \\(\pi(p_n)=n\\) and \\(p_{\pi(n)}=n\\). Now, we consider the function
\\[y=\frac{x}{\log{x}}.\\]
Taking the logarithm of both sides, we obtain,
\\[\log{y}=\log{x}-\log{\log{x}}.\\]
Now, we show that \\(\log{\log{x}}=o(\log{x})\\). By L'Hôpital's rule,
\\[\lim_{x\rightarrow\infty}{\frac{\log{\log{x}}}{\log{x}}}=\lim_{x\rightarrow\infty}{\frac{1}{\log{x}}}=0,\\]
as desired. So now, we can divide the logarithm of \\(y\\) by the logarithm of \\(x\\) to obtain
\\[\frac{\log{y}}{\log{x}}=1-\frac{\log{\log{x}}}{\log{x}}.\\]
In the limit, this approaches 1, so that \\(\log{y}\sim \log{x}\\). Hence, when we have
\\[x=y\log{x},\\]
we have that the LHS is the inverse of \\(y\\), but \\(\log{x}\\) is asymptotic to \\(\log{y}\\), so the inverse of \\(y\\) is asymptotic to \\(y\log{y}\\).

Now, it suffices to show that for two divergent functions \\(f\sim g\\), we must also have \\(f^{-1}\sim g^{-1}\\). Observe that
\\[f^{-1}(f(x))=x\Rightarrow\lim_{x\rightarrow\infty}{\frac{f^{-1}(f(x))}{x}}=1.\\]
Likewise, we have
\\[\lim_{x\rightarrow\infty}{\frac{g^{-1}(g(x))}{x}}=1.\\]
But since \\(f\sim g\\), we can replace \\(g\\) with \\(f\\) in the limit to obtain
\\[\lim_{x\rightarrow\infty}{\frac{g^{-1}(f(x))}{x}}=1.\\]
Dividing our two limits, we obtain
\\[\lim_{x\rightarrow\infty}{\frac{f^{-1}(f(x))}{g^{-1}(f(x))}}=1,\\]
and since \\(f\\) is divergent, we can write this as
\\[\lim_{f(x)\rightarrow\infty}{\frac{f^{-1}(f(x))}{g^{-1}(f(x))}}=1,\\]
so \\(f^{-1}\sim g^{-1}\\), as desired.

Hence, since \\(\pi(n)\sim y\\), the inverse of \\(y\\) is asymptotic to \\(n\log{n}\\), and \\(p_n\\) is the inverse of \\(\pi(n)\\), we have
\\[\boxed{p_n\sim n\log{n}}.\\]