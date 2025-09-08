---
layout: post
title: "Manipulation"
date: 2019-11-24 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
**1994 Wisconsin Mathematics Science & Engineering Talent Search PSET 3 Problem 3:** Find all positive integer solutions of the equation
\\[x^3-y^3=xy+61.\\]
*Solution*: My first instinct is that the LHS factors:
\\[(x-y)(x^2+xy+y^2)=xy+61.\\]
I see that there is an \\(xy\\) term on both sides of the equation. Perhaps if I distribute the \\(x-y\\) on the LHS and then subtract \\(xy\\). Then, we obtain
\\[(x-y)x^2+(x-y-1)xy+(x-y)y^2=61.\\] 
This doesn't do me any good, but I notice that I can factor out \\(x-y\\), I can obtain
\\[(x-y)\left(x^2+\left(1-\frac{1}{x-y}\right)xy+y^2\right)=61.\\]
Aha! Now we can equate the two factors on the left to the integer factors of \\(61\\). Luckily, \\(61\\) is prime so there are only four cases to test. The only one that ends up working is \\(x-y=1\\), which yields
\\[x^2+(x-1)^2=61\Rightarrow 2x^2-2x-60=0\Rightarrow (x-6)(x+5)=0.\\]
So our two integer solutions are \\((6,5)\\) and \\((-5,-6)\\). The only positive integer solution is thus \\(\boxed{(6,5)}\\).

**1994 Wisconsin Mathematics Science & Engineering Talent Search PSET 3 Problem 4:** Without using a calculator or computer, determine which of the two numbers \\(31^{11}\\) or \\(17^{14}\\) is larger.

*Solution 1*: First, I observed that \\(31=2^5-1\\) and \\(17=2^4+1\\). So the ratio between the two given numbers is
\\[\begin{split}
\frac{31^{11}}{17^{14}}&=\frac{(2^5-1)^{11}}{(2^4+1)^{14}}\\\\\
&=\frac{(2^5-1)^{11}}{(2^4+1)^{14}}\cdot\frac{2^{-56}}{2^{-56}}\\\\\
&=\frac{1}{2}\cdot\frac{(1-2^{-5})^{11}}{(1+2^{-4})^{14}}
\end{split}\\]
Since \\(\frac{(1-2^{-5})^{11}}{(1+2^{-4})^{14}}<\frac{(1-2^{-5})^{11}}{1}<\frac{1}{1}\\), we must have \\(17^{14}>31^{11}\\).

*Solution 2*: This time, we proceed with the difference instead of the ratio.
\\[\begin{split}
17^{14}-31^{11}&=(2^4+1)^{14}-(2^5-1)^{11}\\\\\
&=\sum_{k=0}^{14}{\binom{14}{k}2^{56-4k}}-\sum_{j=0}^{11}{(-1)^j\binom{11}{j}2^{55-5j}}\\\\\
&=\sum_{k=0}^{11}{\binom{14}{k}2^{56-4k}+(-1)^{k+1}\binom{11}{k}2^{55-5k}}+\sum_{j=12}^{14}{\binom{14}{j}2^{56-4j}}
\end{split}\\]
The second summation in the last expression above is positive since each term is positive. At this point, I wonder if I could decompose \\(\binom{14}{k}\\) into a linear combination of terms of the form \\(\binom{11}{r}\\). I realize that this is actually possible with Pascal's identity:
\\[\begin{split}
\binom{14}{k}&=\binom{13}{k}+\binom{13}{k-1}\\\\\
&=\binom{12}{k}+2\binom{12}{k-1}+\binom{12}{k-1}\\\\\
&=\binom{11}{k}+3\binom{11}{k-1}+3\binom{11}{k-2}+\binom{11}{k-3}
\end{split}\\]
Curiously, the coefficients themselves are binomial coefficients! The proof of that follows pretty naturally. I bet there is a counting argument for it too. Anyway, our first summation can now be written as:
\\[\begin{split}
\sum_{k=0}^{11}{\binom{14}{k}2^{56-4k}+(-1)^{k+1}\binom{11}{k}2^{55-5j}}&=\sum_{k=0}^{11}{\left[\binom{11}{k}+3\binom{11}{k-1}+3\binom{11}{k-2}+\binom{11}{k-3}\right]2^{56-4k}+(-1)^{k+1}\binom{11}{k}2^{55-5k}}\\\\\
&=\sum_{k=0}^{1}{\binom{11}{k}\left(2^{56-4k}+(-1)^{k+1}2^{55-5k}\right)+\left[3\binom{11}{k-1}+3\binom{11}{k-2}+\binom{11}{k-3}\right]2^{56-4k}}
\end{split}\\]
Observe that for due to the definition of generalized binomial coefficients, \\(\binom{11}{r}=0\\) for negative integers \\(r\\). Furthermore, we observe that to have \\(2^{56-4k}>2^{55-5k}\\), we must have \\(56-4k>55-5k\\) or \\(k>-1\\). But this is obviously always true for our index \\(k\\) which starts at \\(0\\).

Hence, every term in the summations is positive. So we must have \\(\boxed{17^{14}>31^{11}}\\).