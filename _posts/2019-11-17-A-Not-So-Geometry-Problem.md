---
layout: post
title: "A Not-So Geometry Problem"
date: 2019-11-17 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
Here is a fun one.

**1994 Wisconsin Mathematics Science & Engineering Talent Search PSET 3 Problem 2:** Suppose that each of the three main diagonals \\(\overline{AD}\\), \\(\overline{BE}\\), and \\(\overline{CF}\\) divide the hexagon \\(ABCDEF\\) into two regions of equal area. Prove that the three diagonals meet at a common point.

*Solution*: Interesting. First, I drew the proper configuration. Where the diagonals concurred at point \\(P\\) and each split the hexagon into regions of equal area. In this case, six triangles were formed. I let \\(T_1=\triangle APB\\), and likewise labelled the rest of the triangles, proceeding clockwise with the labeling. Writing our three area conditions in terms of the areas of the \\(T_i\\)'s, I obtained the system of equations
\\[\left\\{
\begin{array}{ll}
[T_1]+[T_2]+[T_3]=[T_4]+[T_5]+[T_6]\\\\\
[T_2]+[T_3]+[T_4]=[T_1]+[T_5]+[T_6]\\\\\
[T_1]+[T_2]+[T_6]=[T_3]+[T_4]+[T_5].
\\end{array} \right.\\]
Wow. There is clearly a *massive* amount of symmetry in these equations. My instinct is to add them all together.
\\[3[T_2]+2[T_1]+2[T_3]+[T_4]+[T_6]=3[T_5]+2[T_6]+2[T_4]+[T_1]+[T_3].\\]
This rearranges to
\\[2[T_2]+([T_1]+[T_2]+[T_3])=2[T_5]+([T_4]+[T_5]+[T_6]).\\]
Aha! The sums in the parentheses are equivalent! So \\([T_2]=[T_5]\\). By symmetry, we must also have \\([T_1]=[T_4]\\) and \\([T_3]=[T_6]\\). These results can be obtained explicitly by flipping an equation in our original system before adding all of the equations together.

Conveniently, the triangles with equal areas happen to have equal angles since they are formed by the same two diagonals in each instance. Since the area of a triangle is given by \\([ABC]=\frac{1}{2}ab\sin{C}\\), and the enclosed angles were the same between the pairs of triangles with equal area, the product of the lengths of the enclosing sides must also be the same. So I figured, let \\(AP=a\\), \\(BP=b\\), etc. Then, we must have
\\[\left\\{
\begin{array}{ll}
af=cd\\\\\
de=ab\\\\\
bc=ef.
\end{array}\right.\\]
At this point, I couldn't really immediately see anything more insightful about the correct configuration. I wondered how to even prove concurrency. Perhaps, I could work with a configuration that was *not* correct and show that the configuration could not be correct.

So then, suppose that the three diagonals were *not* concurrent. Then there exists a seventh triangle, \\(T_7=\triangle RST\\), such that \\(R=\overline{AD}\cap\overline{BE}\\), \\(S=\overline{AD}\cap\overline{CF}\\), and \\(T=\overline{BE}\cap\overline{CF}\\). In this case, let \\(T_1=\triangle ASF\\), \\(T_2=\triangle ARB\\), \\(T_3=\triangle BTC\\), \\(T_4=\triangle CSD\\), \\(T_5=\triangle DRE\\), and \\(T_6=\triangle ETF\\).
​
Incredibly, when we write the area conditions out in this configuration, \\([T_7]\\) vanishes entirely! The resulting system is identical to what we obtained in the correct configuration, and once again we obtain \\([T_1]=[T_4]\\), \\([T_2]=[T_5]\\), and \\([T_3]=[T_6]\\). The manipulations required to obtain these equalities are slightly trickier, however, as we have to strategically subtract \\([T_7]\\) from both sides of our simplified sum of three equations.

Anyway, we let \\(RS=\alpha\\), \\(ST=\beta\\), and \\(RT=\gamma\\). We define the length from a vertex \\(V\\) of the hexagon to a vertex of \\(T_7\\) to be the lowercase of \\(V\\). Then, turning our area conditions into length conditions using the product of side lengths, we obtain
\\[\left\\{
\begin{array}{ll}
af=(c+\beta)(d+\alpha)\\\\\
de=(a+\alpha)(b+\gamma)\\\\\
bc=(e+\gamma)(f+\beta).
\end{array}\right.\\]
Again, I see massive symmetry. This time, my instinct is to multiply the three equations together:
\\[abcdef=(a+\alpha)(b+\gamma)(c+\beta)(d+\alpha)(e+\gamma)(f+\beta).\\]
Aha! The product on the RHS is \\(\geq abcdef\\) since every variable is a length, and thus nonnegative. The equality condition is thus only achieved when \\(\alpha=\beta=\gamma=0\\).

In other words, \\(T_7\\) must be a degenerate triangle whose vertices, the pairwise intersections of the main diagonals, must coincide at the same point. \\(\square\\)