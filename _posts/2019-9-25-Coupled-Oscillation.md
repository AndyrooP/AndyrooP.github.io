---
layout: post
title: "Coupled Oscillation"
date: 2019-9-25 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
Sorry for the inactivity. I have just started my studies at the University of California, San Diego.

Here is a method I've learned from *Introductory Classical Mechanics* to solve a certain system of ODEs. Consider a system of ODEs of the form:
\\[\left\\{\begin{array}{ll}\ddot{x}+\omega^2(ax+by)=0\\ \\\ \ddot{y}+\omega^2(cx+dy)=0\\ \end{array}\right.\\]
Such a system often arises from *coupled oscillations*. To solve such equations, we suppose there exists solutions of the form \\(x=Ae^{i\alpha t}\\) and \\(y=Be^{i\alpha t}\\). Substituting these solutions into the the differential equations, we obtain the system of equations
\\[\left\\{\begin{array}{ll}(a\omega^2-\alpha^2)A+b\omega^2B\\\\ c\omega^2A+(d\omega^2-\alpha^2)B\\ \end{array}\right.\\]
We wish to find nontrivial solutions \\(A,B\\) (which in this case means nonzero solutions). It is easier to see the condition for the independent nontrivial solution if we write the system in matrix form:
\\[\begin{bmatrix}
a\omega^2-\alpha^2 & b\omega^2 \\\\\
c\omega^2 & d\omega^2-\alpha^2
\end{bmatrix}
\begin{bmatrix}
A \\\\\
B
\end{bmatrix}=
\begin{bmatrix}
0 \\\\\
0
\end{bmatrix}.
\\]
Let \\(\mathbf{M}\\) be the first matrix and \\(\mathbf{N}\\) be the second matrix in the above equation. Then, if \\(\mathbf{M}\\) is invertible, then multiplying through with its inverse would yield \\(\mathbf{N}=0\\), the solutions that we wish to avoid. Hence, if nontrivial solutions are to exist, \\(\mathbf{M}\\) cannot be invertible.

The inverse of \\(\mathbf{M}\\) is the adjugate matrix of \\(\mathbf{M}\\) divided by the determinant of \\(\mathbf{M}\\). So if we wish for this to not exist, the determinant of \\(\mathbf{M}\\) must be zero. That is,
\\[\begin{vmatrix}
a\omega^2-\alpha^2 & b\omega^2 \\\\\
c\omega^2 & d\omega^2-\alpha^2
\end{vmatrix}=\alpha^4-(a+d)\omega^2\alpha^2+(ad-bc)\omega^4=0.\\]
We can view this multivariate polynomial as biquadratic in \\(\alpha\\). We solve the biquadratic by letting \\(\beta=\alpha^2\\) and then using the quadratic formula.
\\[\beta=\frac{1}{2}\left[a+d\pm\sqrt{(a-d)^2+4bc}\right]\omega^2.\\]
Hence, we have four solutions for \\(\alpha\\):
\\[\alpha=\pm\frac{\omega}{\sqrt{2}}\sqrt{a+d\pm\sqrt{(a-d)^2+4bc}}.\\]
Suppose that these solutions are \\(\pm R\omega\\) and \\(\pm S\omega\\). We can then obtain
\\[A=-\frac{b}{a-R^2}B\\]
\\[A=-\frac{b}{a-S^2}B,\\]
We can now use the principle of superposition to write the general solution as
\\[\begin{bmatrix}
x \\\\\
y
\end{bmatrix}=A_1\begin{bmatrix}
1 \\\\\
-\frac{b}{a-R^2}
\end{bmatrix}e^{iR\omega t}+A_2\begin{bmatrix}
1 \\\\\
-\frac{b}{a-R^2}
\end{bmatrix}e^{-iR\omega t}+A_3\begin{bmatrix}
1 \\\\\
-\frac{b}{a-S^2}
\end{bmatrix}e^{iS\omega t}+A_4\begin{bmatrix}
1 \\\\\
-\frac{b}{a-S^2}
\end{bmatrix}e^{-iS\omega t}\\]
Where the coefficients \\(A_i\\) are determined by initial conditions. Depending on the \\(A_i\\), we can condense the exponentials into, for instance, sinusoidal functions.

This sort of system of ODEs appears most often with coupled oscillation. This post was way overdue. Sorry. UC San Diego is keeping me busy. I'll grind this weekend to catch up on stuff on this website.