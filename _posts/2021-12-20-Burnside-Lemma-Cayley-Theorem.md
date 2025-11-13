---
layout: post
title: "Burnside's Lemma and Cayley's Theorem"
date: 2021-12-20 12:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Group actions are a powerful tool for establishing some very concrete results. One classic application is the classification of the finite subgroups of \\(\mathrm{SO}(3)\\). We will explore group actions more by establishing Burnside's lemma and Cayley's theorem.

The central result in the theory of group actions is the orbit-stabilizer theorem. For a group \\(G\\) acting on a set \\(S\\), and for any fixed \\(s\in S\\), the orbit-stabilizer theorem establishes the existence of a bijection between the set of cosets of the stabilizer of \\(s\\) in \\(G\\) and the orbit of \\(s\\). Combining this with the counting formula tells us that if \\(G_s\\) is the stabilizer of \\(s\\) and \\(O_s\\) is the orbit of \\(s\\), we must have
\\[|G|=|G_s||O_s|\\]
​if \\(G\\) is finite. This fact enables us to prove the following result.

**Burnside's Lemma:** Let \\(G\\) be a finite group acting on the finite set \\(S\\). For each \\(s\in S\\) let \\(S_g=\\{s\in S\colon gs=s\\}\\). If \\(N\\) is the number of orbits induced by the group action, then
\\[|G|\cdot N=\sum_{g\in G}{|S^g|}.\\]

_Proof​_: Let us label the unique orbits as \\(O_{s_1},\dots,O_{s_N}\\). Since the orbits partition \\(S\\), we have
\\[\begin{split}
\sum_{s\in S}{\frac{1}{|O_s|}}&=\sum_{j=1}^{N}{\sum_{s\in O_{s_j}}{\frac{1}{|O_s|}}}\\\\\
&=\sum_{j=1}^{N}{1}\\\\\
&=N.
\end{split}\\]
Multiplying both sides by \\(|G|\\) gives us
\\[|G|\cdot N=\sum_{s\in S}{\frac{|G|}{|O_s|}}.\\]
Let \\(G_s\\) be the stabilizer of \\(s\\). By the counting formula, we can rewrite the summand to obtain
\\[|G|\cdot N=\sum_{s\in S}{|G_s|}.\\]
Consider every formula of the form \\(gs=s\\) that is true under the group action, where \\(g\in G\\) and \\(s\in S\\). Each such formula corresponds to exactly one element in \\(G_s\\) (namely \\(g\\)) and one element in \\(S^g\\) (namely \\(s\\)). Conversely, every element in \\(G_s\times \\\{s\\\}\\) corresponds to exactly one formula of the aforementioned form, and similarly every element in \\(S^g\times \\\{g\\\}\\) corresponds to exactly one formula of the aforementioned form. So the following diagram commutes:
<div style="text-align: center;">
<img src="/myassets/images/2021-12-20-Burnside-Lemma-Cayley-Theorem/dia1.png" alt="diagram" width="1000px">
</div>
where \\(F\\) is the set of all formulas of the aforementioned form and all of the arrows are bijections. In particular, the bijection \\(\bigsqcup_{s\in S}{G_s}\leftrightarrow\bigsqcup_{g\in G}{S^g}\\) implies that
​\\[\sum_{s\in S}{|G_s|}=\sum_{g\in G}{|S^g|},\\]
and we are done. \\(\square\\)

​Burnside's lemma finds application in places where we wish to compute the number of orbits \\(N\\). For instance, consider the set \\(S\\) of \\(\binom{8}{4}=70\\) colorings of an octagon where four of the edges must be black and the other four must be white. Since it forms the symmetries of the octagon, the dihedral group \\(D_8\\) acts on this set, and we may consider orbits of this action to correspond to unique colorings. How many unique colorings are there?

By Burnside's lemma, the answer is \\(\frac{1}{16}\sum\_{g\in D^8}{\|S^g\|}\\). Notice by our work above, this is the same thing as \\(\frac{1}{16}\sum\_{s\in S}{\|G^s\|}\\). Why do we bother using the former sum over the latter? More deeply, why did Burnside (actually, <a href="https://en.wikipedia.org/wiki/Burnside's_lemma#History:_the_lemma_that_is_not_Burnside's" target="_blank">it wasn't him</a>) care more about expressing \\(N\\) in terms of \\(\sum_{g\in G}{\|S^g\|}\\) rather than \\(\sum_{s\in S}{\|G_s\|}\\)?

Our example hints at the answer. \\(S^g\\) represents the subset of colorings that remain fixed by the single symmetry \\(g\\). On the other hand, \\(G_s\\) represents the subgroup of symmetries that remain fixed by the single coloring \\(s\\). A little bit of thought is sufficient to see that \\(S^g\\) is in general a _much_ simpler object to understand than \\(G_s\\). This holds in general: if the group acting on the set has a very complicated structure, it is very difficult to study the subgroup of it that fixes a single element of the set that it acts on. On the other hand, sets do not have any structure—they only have elements. By holding a group element fixed, the task becomes a matter of checking which elements in the set are fixed by that group element. This is a much easier task as it avoids the trouble of dealing with a potentially complicated group structure. In our case, this is to say that it is much easier to find the set of colorings that remain fixed under a given symmetry of the octagon than it is to find the set of symmetries that fix a given coloring of the octagon.

​We can push group actions even further. Let \\(G\\) be a group. Let \\(S\\) be a set, and let \\(\mathrm{Perm}\ S\\) denote its permutations. Note that in the category of sets, the morphisms are just functions, so \\(\mathrm{Perm}\ S\\) is really just the automorphism group of \\(S\\). In particular, it has a group structure, and there may exist a homomorphism \\(\varphi\colon G\to\mathrm{Perm}\ S\\). Such a homomorphism is called a _permutation representation_ of \\(G\\) (with respect to \\(S\\)).

It is not hard to see that the set of group actions of \\(G\\) on \\(S\\) has a bijective correspondence with the set of permutation representations of \\(G\\) with respect to \\(S\\). For example, let \\(A\\) be a group action. Then it can be checked that the map \\(\varphi_A\colon G\to S_n\\) which sends \\(g\in G\\) to the automorphism on \\(S\\) which is \\(A\\)-multiplication by \\(g\\) is indeed a homomorphism. Conversely, it may be checked that any permutation representation defines an action of \\(G\\) on \\(S\\).

This natural correspondence gives us a natural way to identify group actions. If the permutation representation corresponding to a group action is injective, we say that the group action is _faithful_. Faithfulness is of course equivalent to the kernel of the corresponding permutation representation being trivial. The identity element of \\(\mathrm{Perm}\ S\\) is of course the identity map from \\(S\\) to itself. So for the kernel to be trivial, we wish left-multiplication by \\(g\\) to emulate the identity map on \\(S\\) precisely when \\(g\\) is the identity element of \\(G\\). We are now ready to prove a result that seems very deep to me at least.

​**Cayley's Theorem:** Every finite group of order \\(n\\) is isomorphic to a subgroup of the symmetric group \\(S_n\\).

_Proof_: Let \\(G\\) be a finite group. Consider the group action of \\(G\\) on itself that maps \\((g,x)\mapsto gx\\). There exists a permutation representation of \\(G\\) with respect to itself, namely the homomorphism \\(\varphi\colon G\to\mathrm{Perm}\ G\\) that maps \\(g\\) to the automorphism on \\(G\\) that is left-multiplication by \\(g\\). Of course, the only element \\(g\in G\\) such that \\(gx=x\\) for every \\(x\in G\\) is the identity, so this group action is faithful. In particular, \\(\varphi\\) is an injective homomorphism, so \\(G\\) is isomorphic to \\(\varphi(G)\\). But of course, \\(\mathrm{Perm}\ G\\) is isomorphic to \\(S_n\\) where \\(n=\|G\|\\). \\(\square\\)

So in an abstract sense, the symmetric groups are complicated enough that they encode every other possible finite group. This is an interesting result. However, it turns out that the idea of a group acting on itself is what really matters here, and it is that concept which is eventually used to obtain the Sylow theorems.