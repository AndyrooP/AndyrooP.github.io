---
layout: post
title: "Varignon's Theorem"
date: 2019-6-2 01:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Here are some problems from *Multivariable and Vector Calculus* by David Santos.

**Varignon's Theorem:** The quadrilateral formed by midpoints of sides of any quadrilateral is a parallelogram.

**Proof:** We proceed by vectors. Let our arbitrary quadrilateral be \\(ABCD\\), and let \\(W\\) be the midpoint of \\(\overline{AB}\\), \\(X\\) be the midpoint of \\(\overline{BC}\\), etc.

Observe that it suffices to show that \\(\mathbf{ZW}+\mathbf{ZY}=\mathbf{ZX}\\).

We see that \\(\mathbf{ZW}=\mathbf{ZA}+\mathbf{AW}\\). Furthermore, \\(\mathbf{ZY}=\mathbf{ZD}+\mathbf{DY}=-\mathbf{ZA}+\mathbf{DY}\\). Adding these two equations yields:
\\[\mathbf{ZW}+\mathbf{ZY}=\mathbf{AW}+\mathbf{DY}\\]
We take a look at \\(\mathbf{AW}\\) and find \\(\mathbf{AW}=\mathbf{WB}\\) and \\(\mathbf{WB}=\mathbf{WX}-\mathbf{BX}\\), hence \\(\mathbf{AW}=\mathbf{WX}-\mathbf{BX}\\). In a similar manner we may show that \\(\mathbf{DY}=\mathbf{YX}-\mathbf{CX}=\mathbf{YX}+\mathbf{BX}\\). Therefore:
\\[\mathbf{AW}+\mathbf{DY}=\mathbf{YX}+\mathbf{WX}\\]
And so:
\\[\mathbf{ZW}+\mathbf{ZY}=\mathbf{YX}+\mathbf{WX}\\]
We're almost done. We add \\(\mathbf{YX}+\mathbf{WX}\\) to both sides to obtain:
\\[\mathbf{ZW}+\mathbf{WX}+\mathbf{ZY}+\mathbf{YX}=2\left(\mathbf{YX}+\mathbf{WX}\right)\\]
This simplifies to:
\\[2\mathbf{ZX}=2\left(\mathbf{YX}+\mathbf{WX}\right)=2\left(\mathbf{ZW}+\mathbf{ZY}\right)\\]
And dividing by \\(2\\), we obtain the desired result. \\(\square\\)


**Problem:** Let \\(X\\), \\(Y\\), and \\(Z\\) be points on the plane with \\(X\neq Y\\). Demonstrate that the point \\(A\\) belongs to \\(\overleftrightarrow{XY}\\) if and only if there exists scalars \\(\alpha,\beta\\) with \\(\alpha+\beta=1\\) such that:
\\[\mathbf{ZA}=\alpha\mathbf{ZX}+\beta\mathbf{ZY}\\]

**Solution:** We define \\(\overleftrightarrow{XY}\\) to be the standard horizontal axis. Then, the component of any vector from \\(Z\\) to \\(\overleftrightarrow{XY}\\) orthogonal to \\(\overleftrightarrow{XY}\\) must be a constant. Hence we may write:
\\[\mathbf{ZX}=\left<a,k\right>\\]
\\[\mathbf{ZY}=\left<b,k\right>\\]
Suppose \\(\exists\alpha,\beta\\) such that \\(\mathbf{ZA}=\alpha\mathbf{ZX}+\beta\mathbf{ZY}\\) and \\(\alpha+\beta=1\\). Then it follows that we may write:
\\[\mathbf{ZA}=\left<\alpha a+\beta b,(\alpha+\beta)k\right>\\]
But since \\(\alpha+\beta=1\\), this becomes:
\\[\mathbf{ZA}=\left<\alpha a+\beta b,k\right>\\]
Since the component orthogonal to \\(\overleftrightarrow{XY}\\) of \\(\mathbf{ZA}\\) is equal to the constant \\(k\\), \\(A\\) must lie on \\(\overleftrightarrow{XY}\\).

The converse of the above is also true. Suppose that \\(A\\) does lie on \\(\overleftrightarrow{XY}\\). Then:
\\[\mathbf{ZA}=\left<c,k\right>\\]
It is possible to uniquely determine \\(\alpha,\beta\\) that satisfy:
\\[\left\\{\begin{array}{ll}\alpha a+\beta b=c\\\ \alpha+\beta=1\\ \\end{array}\right.\\]
By solving the system of equations above. A unique solution exists because we are given \\(X\neq Y\\) and thus \\(a\neq b\\), so the system is independent.

Those values of \\(\alpha\\) and \\(\beta\\) permit the relation:
\\[\mathbf{ZA}=\alpha\mathbf{ZX}+\beta\mathbf{ZY}\\]
Hence, \\(A\\) lies on \\(\overleftrightarrow{XY}\\) iff \\(\alpha\\) and \\(\beta\\) exist as described. \\(\square\\)