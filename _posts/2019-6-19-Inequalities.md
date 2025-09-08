---
layout: post
title: "Inequalities"
date: 2019-6-19 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Here are some inequalities I solved today/yesterday.

**Problem (USAMTS):** Find the ordered pair of real numbers \\((x,y)\\) that satisfies the equation below, and demonstrate that it is unique:
\\[\frac{36}{\sqrt{x}}+\frac{9}{\sqrt{y}}=42-9\sqrt{x}-\sqrt{y}.\\]

*Solution*: The equation rearranges as:
\\[\frac{36}{\sqrt{x}}+9\sqrt{x}+\frac{9}{\sqrt{y}}+\sqrt{y}=42.\\]
Next, observe that by AM-GM:
\\[\frac{36}{\sqrt{x}}+9\sqrt{x}\geq2\sqrt{36\cdot9}=36,\\]
and:
\\[\frac{9}{\sqrt{y}}+\sqrt{y}\geq2\sqrt{9}=6.\\]
Adding these two inequalities yields:
\\[\frac{36}{\sqrt{x}}+9\sqrt{x}+\frac{9}{\sqrt{y}}+\sqrt{y}\geq42,\\]
so our equation is actually just the equality condition of AM-GM applied to \\(x\\) and \\(y\\) terms separately. Equality in AM-GM holds *only* when the terms are equal, hence the solution to the equation is unique. We have:
\\[\frac{36}{\sqrt{x}}=9\sqrt{x}\Rightarrow\boxed{x=\frac{36}{9}},\\]
and:
\\[\frac{9}{\sqrt{y}}=\sqrt{y}\Rightarrow\boxed{y=9}.\\]

**Problem:** Show that for all positive real numbers \\(x\neq1\\) and nonnegative integers \\(n\\), we have
\\[\frac{x^{2n+1}-1}{x^{n+1}-x^n}\geq2n+1.\\]

*Solution*: Observe that the LHS can be rewritten:
\\[\begin{split}
\frac{x^{2n+1}-1}{x^{n+1}-x^n}&=\frac{x^{2n+1}-1}{x^n(x-1)}\\
&=\frac{x^{n+1}-\frac{1}{x^n}}{x-1}\\
&=\frac{\frac{1}{x^n}(1-x^{2n+1})}{1-x}.
\end{split}\\]
This is the sum of a finite geometric series with first term \\(\frac{1}{x^n}\\), common ratio \\(x\\), and \\(2n+1\\) terms. Therefore, our inequality can be written as
\\[x^{-n}+x^{-n+1}+...+x^n\geq2n+1.\\]
But this is true by AM-GM on the LHS.

Since all of our steps are reversible, we are done. \\(\square\\)

**Problem:** Show that for all positive integers \\(n\\) with \\(n\geq2\\), we have
\\[\frac{1}{n}+\frac{1}{n+1}+...+\frac{1}{2n-1}>n(2^{1/n}-1).\\]

*Solution*: We rearrange the inequality to:
\\[\frac{\frac{1}{n}+\frac{1}{n+1}+...+\frac{1}{2n-1}}{n}+1>2^{1/n}.\\]
This is simply:
\\[\frac{n+\frac{1}{n}+\frac{1}{n+1}+...+\frac{1}{2n-1}}{n}>2^{1/n}.\\]
Now, we break up the \\(n\\) in the numerator into \\(n\\) ones and allocate the ones to every remaining term in the numerator:
\\[\frac{\left(1+\frac{1}{n}\right)+\left(1+\frac{1}{n+1}\right)+...+\left(1+\frac{1}{2n-1}\right)}{n}>2^{1/n}.\\]
But now, this becomes:
\\[\frac{\frac{n+1}{n}+\frac{n+2}{n+1}+...+\frac{2n}{2n-1}}{n}>2^{1/n},\\]
which is true by AM-GM. Observe that the inequality is strict since obviously none of the terms in the numerator are equal (which is the equality condition for AM-GM).

Since all our steps are reversible, we are done. \\(\square\\)

I didn't find (or solve) any interesting Cauchy-Schwarz problems. :(. Tomorrow/today I think I will work on combo.