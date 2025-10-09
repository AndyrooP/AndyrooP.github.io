---
layout: post
title: "Cracking an interesting problem in linear algebra"
date: 2020-12-13 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
It is easy to see that the set of all \\(3\times3\\) real matrices, which I will denote by \\(\mathbb{M}\_{3\times3}\\) is a vector space. Consider \\(H\subset\mathbb{M}\_{3\times3}\\) defined by
\\[H=\{A\in\mathbb{M}\_{3\times3}\ \text{such that }\det{(A+A^T)}=0\}.\\]
Is \\(H\\) a subspace of \\(\mathbb{M}\_{3\times3}\\)?

It turns out, the answer is no. \\(H\\) has a zero element and is closed under scalar multiplication, but it is _not_ closed under vector addition. It is sufficient to find \\(A,B\in H\\) with \\(A+B\notin H\\).

Easy, right? Just take
\\[A=\begin{bmatrix}
1 & 2 & 1\\\\\
2 & 1 & 2\\\\\
1 & 2 & 1
\end{bmatrix}\\]
\\[B=\begin{bmatrix}
\sqrt{2} & \sqrt{3} & 2\sqrt{2}\\\\\
\sqrt{3} & \sqrt{2} & \sqrt{3}\\\\\
2\sqrt{2} & \sqrt{3} & \sqrt{2}
\end{bmatrix},\\]
and we are done. \\(\square\\)

As satisfying it would be to just leave these matrices without any trace of where they come from, it contradicts the mantra: _a slick write-up is not an instructional one_.

The first thing to observe is that a matrix plus its transpose is always a symmetric matrix. This is easy to show (addition on real numbers is commutative). So the condition \\(\det{(A+A^T)}=0\\) is really saying that a certain symmetric matrix related to \\(A\\) is singular.

Moreover, if a matrix is already symmetric, then it is equal to its transpose. This means that the sum of itself with its transpose is equal to two times itself. That is, if \\(A\\) is a symmetric, \\(A+A^T=2A\\). But determinants are multilinear (linear on each column vector). So \\(\det{2A}=2^n\det{A}\\), if \\(A\\) is an \\(n\times n\\) matrix. This means that if we choose a symmetric \\(A\in\mathbb{M}_{3\times3}\\) that is singular, then \\(A\in H\\), since \\(\det{(A+A^T)}=\det{2A}=8\det{A}=0\\).

In other words, if we choose a symmetric matrix from \\(H\\), instead of worrying about the sum of that matrix with its transpose, we can just focus on the matrix itself (that is, if \\(A\\) is symmetric, then \\(\det{(A+A^T)}=0\\) if and only if \\(\det{A}=0\\)). So let's investigate symmetric \\(3\times3\\) matrices. They look like this
\\[S=\begin{bmatrix}
a & b & c\\\\\
b & d & e\\\\\
c & e & f
\end{bmatrix}.\\] 
Full disclosure: I stumbled upon <a href="https://math.stackexchange.com/questions/603213/are-there-simple-methods-for-calculating-the-determinant-of-symmetric-matrices" target="_blank">this SE post</a> which inspired me to consider the special case of a \\(3\times3\\) symmetric matrix where \\(d=f=a\\) and \\(e=b\\):
\\[S=\begin{bmatrix}
a & b & c\\\\\
b & a & b\\\\\
c & b & a
\end{bmatrix}.\\]
​We compute the determinant of such a matrix.
\\[\begin{split}
\det{S}&=a(a^2-b^2)-b(ab-bc)+c(b^2-ac)\\\\\
&=a(a^2-b^2)-b^2(a-c)+b^2c-ac^2\\\\\
&=a^3-b^2a+b^2c-ac^2-b^2(a-c)\\\\\
&=a(a+c)(a-c)-b^2(a-c)-b^2(a-c)\\\\\
&=(a-c)(a^2+ac-2b^2).
\end{split}\\]
In essence, there are three ways that this special case symmetric matrix can be singular. Either only the first factor is equal to zero, only the second factor is equal to zero, or both factors are equal to zero.

The sum of two symmetric matrices is also a symmetric matrix, so applying our previous reasoning, instead of worrying about the determinant \\(\det{(A+B+(A+B)^T)}\\), if we select \\(A\\) and \\(B\\) to be symmetric, we need to only worry about \\(\det{(A+B)}\\). Now watch what happens if we let \\(A\\) and \\(B\\) be special-case symmetric matrices in \\(H\\) with \\(A\\) having _only_ the first factor in its determinant equal to zero and \\(B\\) having _only_ the second factor in its determinant equal to zero. In other words, write
\\[A=\begin{bmatrix}
a & b & c\\\\\
b & a & b\\\\\
c & b & a
\end{bmatrix}\\]
\\[B=\begin{bmatrix}
x & y & z\\\\\
y & x & y\\\\\
z & y & x
\end{bmatrix}\\]
with \\(a-c=0\neq a^2+ac-2b^2\\), and \\(x^2-xz-2y^2=0\neq x-z\\). In that case,
\\[A+B=\begin{bmatrix}
p & q & r\\\\\
q & p & q\\\\\
r & q & p
\end{bmatrix},\\]
where \\(p=a+x\\), \\(q=b+y\\), and \\(r=c+z\\). Clearly then it follows that
\\[p-r=a+x-c-z=x-z\neq0,\\]
\\[p^2-pr-2q^2=(a+x)^2-(a+x)(c+z)-2(b+y)^2=a^2+ac-2b^2+2ax-az-cx-4by=\xi.\\]
So as long as we choose \\(a,b,c,x,y,z\\) such that \\(\xi\\) is nonzero, the determinant of \\(A+B\\) is guaranteed to be nonzero! This is easy to accomplish. Setting \\(a=c=1\\) and \\(b=2\\) satisfies our conditions for the matrix \\(A\\). Setting \\(x=\sqrt{2}\\), \\(y=\sqrt{3}\\), and \\(z=2\sqrt{2}\\) satisfies our conditions for matrix \\(B\\), and some quick algebra verifies that \\(\xi\neq0\\). The result follows!

Definitely a fun problem. I reckon there is a simpler solution. My apartment-mate found a counterexample against the closure of \\(H\\) under addition by trying random things on Matlab. I haven't yet looked into why that solution works, and its corresponding generalization. Stick around for updates!