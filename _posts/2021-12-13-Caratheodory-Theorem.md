---
layout: post
title: "Constructing Measures: Carathéodory's Theorem"
date: 2021-12-13 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
There are certain theoretical preliminaries that precede the construction of most measures. One example of a measure that is more or less immediate from the definition of measures is the *counting measure*. It is the measure \\(\mu\\) on the measurable space \\((X,\mathscr{P}(X))\\) given by
\\[\mu(E)=\sum_{x\in E}{1}.\\]
It is intuitive that this ought to be a measure, and it is easily checked that it is one. However, the modern construction of most other "nice" measures requires quite a bit of ground work. The first important result towards this direction is the following.

**Carathéodory's Theorem:** Let \\(\mu^\*\\) be an outer measure on \\(X\\). The collection \\(\mathscr{M}\\) of \\(\mu^\*\\)-measurable subsets of \\(X\\) is a \\(\sigma\\)-algebra on \\(X\\), and the restriction of \\(\mu^\*\\) to \\(\mathscr{M}\\) is a complete measure.

As a side note, the idea of \\(\mu^\*\\)-measurability is sometimes called the <a href="https://en.wikipedia.org/wiki/Carath%C3%A9odory%27s_criterion" target="_blank">*Carathéodory criterion*</a> which is that a subset \\(A\\) is \\(\mu^\*\\)-measurable if for every \\(B\\) in the power set of \\(X\\), we have that \\(\mu^\*(B)=\mu^\*(A\cap B)+\mu^\*(A^c\cap B)\\).

*Proof*: It is clear by the definition of the Carathéodory criterion, and the fact that \\((A^c)^c=A\\), \\(\mathscr{M}\\) is closed under complements. It remains to show that \\(\mathscr{M}\\) is closed under countable unions to establish that it is a \\(\sigma\\)-algebra. First we show that it is closed under finite unions. Suppose \\(A,B\in\mathscr{M}\\). Let \\(E\\) be an arbitrary subset of \\(X\\). Then, since \\(A\\) is \\(\mu^\*\\)-measurable,
\\[\mu^\*(E)=\mu^\*(E\cap A)+\mu^\*(E\cap A^c).\\]
We can split up the first term using the \\(\mu^\*\\)-measurability of \\(B\\). This gives us
\\[\mu^\*(E)=\mu^\*((E\cap A)\cap B)+\mu^\*((E\cap A)\cap B^c)+\mu^\*(E\cap A^c).\\]
Performing a similar expansion on the last term gives us
\\[\mu^\*(E)=\mu^\*(E\cap A\cap B)+\mu^\*(E\cap A\cap B^c)+\mu^\*(E\cap A^c\cap B)+\mu^\*(E\cap A^c\cap B^c).\\]
In fact, the Carathéodory criterion is the natural condition on sets that allows them to be "building blocks" of other sets in the \\(\mu^\*\\) sense. That is, for any finite collection of \\(n\\) \\(\mu^\*\\)-measurable sets, the outer measure of any set can be expressed as the sum of the outer measures of intersections of the set with the \\(2^n\\) pieces that the collection forms.
​

Now, observe that by Venn diagram, \\(A\cup B=(A\cap B)\cup(A\cap B^c)\cup(A^c\cap B)\\). It follows that \\(E\cap(A\cup B)=(E\cap A\cap B)\cup(E\cap A\cap B^c)\cup(E\cap A^c\cap B)\\). Subadditivity then yields
\\[\mu^\*(E\cap(A\cup B))\leq\mu^\*(E\cap A\cap B)+\mu^\*(E\cap A^c\cap B)+\mu^\*(E\cap A\cap B^c).\\]
To this, we add the De Morgan's law identity \\(\mu^\*(E\cap(A\cup B)^c)=\mu^\*(A\cap A^c\cap B^c)\\) to obtain
\\[\mu^\*(E\cap (A\cup B))+\mu^\*(E\cap(A\cup B)^c)\leq\mu^\*(E).\\]
Of course, the reverse inequality follows immediately from subadditivity. Hence, \\(\mathscr{M}\\) is closed under finite unions and is at least an algebra.

The outer measure is also at least finitely additive take \\(A,B\in\mathscr{M}\\) to be disjoint. Then, we have
\\[\mu^\*(A\cup B)=\mu^\*((A\cup B)\cap A)+\mu^\*((A\cup B)\cap A^c)=\mu^\*(A)+\mu^\*(B).\\]

​We need to extend these results to the countable case in order to establish the first part of the theorem. It suffices to consider a countable collections of disjoint sets from \\(\mathscr{M}\\), because the union of arbitrary countable collections from \\(\mathscr{M}\\) can be expressed as the union of a countable collection of disjoint sets from \\(\mathscr{M}\\) via the standard trick. So we let \\(A_1,A_2,\dots\in\mathscr{M}\\) be pairwise disjoint. Define
\\[B_n=\bigcup_{j=1}^{n}{A_j}\qquad B=\bigcup_{j=1}^{\infty}{A_j}.\\]
​For any \\(n\\), since \\(A_n\in\mathscr{M}\\), we have that
\\[\mu^\*(E\cap B_n)=\mu^\*(E\cap B_n\cap A_n)+\mu^\*(E\cap B_n\cap A_n^c).\\]
By definition, the first term is \\(\mu^\*(E\cap A_n)\\) while the second term is \\(\mu^\*(E\cap B_{n-1})\\). Repeating this inductively, we obtain that
\\[\mu^\*(E\cap B_n)=\sum_{j=1}^{n}{\mu^\*(E\cap A_j)}.\\]
​Now, observe that \\(B_n\subseteq B\\), so \\(B^c\subseteq B_n^c\\) and \\(E\cap B^c\subseteq E\cap B_n^c\\). By monotonicity, we then have that \\(\mu^\*(E\cap B^c)\leq\mu^\*(E\cap B_n^c)\\). To this we add the identity above (reversed) to obtain
\\[\mu^\*(E\cap B^c)+\sum_{j=1}^{n}{\mu^\*(E\cap A_j)}\leq\mu^\*(E\cap B_n^c)+\mu^\*(E\cap B_n)=\mu^\*(E).\\]
The far RHS comes from the fact that \\(B_n\in\mathscr{M}\\), since we have already established that \\(\mathscr{M}\\) is an algebra. Now, we take \\(n\to\infty\\) so that
\\[\begin{split}
\mu^\*(E)&\geq\mu^\*(E\cap B^c)+\sum_{j=1}^{\infty}{\mu^\*(E\cap A_j)}\\
&\geq\mu^\*(E\cap B^c)+\mu^\*\left(\bigcup_{j=1}^{\infty}{E\cap A_j}\right)\\
&=\mu^\*(E\cap B^c)+\mu^\*(E\cap B)\\
&\geq\mu^\*(E).
\end{split}\\]
The second line comes from countable subadditivity, the third line is by definition, and the last line comes from finite subadditivity. Note that we cannot immediately suppose that we have equality in the last line, because that would assume that \\(B\in\mathscr{M}\\), which is what we want to show in the first place. In any case, we have bounded \\(\mu^\*(E\cap B^c)+\mu^\*(E\cap B)\\) above and below by \\(\mu^\*(E)\\), so in fact we *do* have equality in the last line. This establishes that \\(\mathscr{M}\\) is a \\(\sigma\\)-algebra. Countable additivity on \\(\mathscr{M}\\) comes immediately by taking \\(E=B\\).

It remains to show that \\(\mu^\*|_{\mathscr{M}}\\) is a complete measure. We already know that \\(\mu^\*\\) will vanish on subsets of null sets by monotonicity. So we just need to show that subsets of null sets in \\(\mathscr{M}\\) are themselves in \\(\mathscr{M}\\). Let \\(\mu^\*(A)=0\\). Then, by subadditivity, \\(\mu^\*(E)\leq\mu^\*(E\cap A)+\mu^*(E\cap A^c)\\), while by monotonicity, \\(\mu^\*(E\cap A)=0\\) and \\(\mu^\*(E\cap A^c)\leq\mu^\*(E)\\), hence,
\\[\mu^\*(E)\leq\mu^\*(E\cap A^c)\leq\mu^\*(E).\\]
Hence, \\(A\\) is \\(\mu^\*\\)-measurable. In particular, if \\(A'\subseteq A\\) then we know that \\(\mu^\*(A')=0\\) and by the above, \\(A'\in\mathscr{M}\\). We are done. \\(\square\\)

Combining Carathéodory's theorem with the fact that premeasures on an algebra induce an outer measure, and every set in the algebra is measurable with respect to that outer measure, one can establish that a premeasure on an algebra can be extended to a measure on the generated \\(\sigma\\)-algebra. In fact: it is precisely the restriction of the induced outer measure to the generated \\(\sigma\\)-algebra.  It turns out that this is the natural extension of the premeasure in the sense that the extension is unique if the premeasure is \\(\sigma\\)-finite, and in the general case, any other measure that extends the premeasure will be equal to the extension defined above on sets with finite measure.

The construction of the Lebesgue measure thus proceeds by defining the natural premeasure on the set of half-open half-closed intervals on the real line, checking that this indeed a premeasure on an algebra, and then invoking the above result which tells us that it extends to a measure on the Borel \\(\sigma\\)-algebra of \\(\mathbb{R}\\). The completion of this measure is what we call Lebesgue measure.

Taking the completion explodes the domain of the measure to a pretty large \\(\sigma\\)-algebra. In fact, the \\(\sigma\\)-algebra of Lebesgue measurable sets is so large that it has been shown that it is impossible to show that there is a Lebesgue nonmeasurable set without the axiom of choice. See <a href="https://en.wikipedia.org/wiki/Solovay_model" target="_blank">here</a>.