---
layout: post
title: "Direct Sums"
date: 2020-7-12 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
There is a notion of direct sums that I've known, but it has always bothered me that I never really had a feel for what it really is. Here I will attempt to construct an analogy between a sum of vector spaces and a union of sets, and in doing so, construct an analogy between a *direct sum* of vector spaces and a *disjoint union* of sets.

It is already well-known (to me) that the dimension of a vector space is in some sense a measure of how *large* that vector space is. This is made apparent by <a href="https://math.stackexchange.com/questions/3484097/is-this-use-of-bijections-for-comparing-infinite-cardinalities-correct" target="_blank">this</a> incorrect proof (see the comment to see why the argument is flawed) of the fact that if a linear transformation is injective, then the dimension of the domain must be at most the dimension of the codomain, and that if the linear transformation is surjective, then the dimension of the domain must be at least the dimension of the codomain. While these statements are easily proven with the rank-nullity theorem, the approach in the incorrect proof imply that, for instance, if \\(\dim{V}>\dim{W}\\), then \\(\|V\|\geq\|W\|\\). So in some sense, the dimension represents how "large" a vector space is.

This plays out in the following problem.

**Problem:** Suppose \\(U_1,\dotsc,U_m\\) are finite-dimensional subspaces of \\(V\\). Prove that \\(U_1+\dots+U_m\\) is finite-dimensional and
\\[\dim{(U_1+\dots+U_m)}\leq\dim{U_1}+\dots+\dim{U_m}.\\]

*Solution*: Any vector in \\(U_1+\dots+U_m\\) can be written as a sum of vectors from each subspace, which themselves can be written as a linear combination of basis vectors of the respective subspaces. So vector can be written as a linear combination of all of these basis vectors. But across subspaces, the basis vectors may not be linearly independent, so we can extract a basis across all of the subspaces from the union of the sets of basis vectors from each subspace, since any spanning set contains a basis. The conclusion follows. \\(\square\\)

We make a key observation in this solution. The strict inequality condition of the problem statement is that a basis vector in one subspace is not linearly independent to other basis vectors in the union of the sets of basis vectors from each subspace. That is, the equality condition is that all of the basis vectors across the subspaces are linearly independent.

As it turns out, this is *precisely* what occurs only when the sum of the subspaces is a direct sum. That is, a direct sum of subspaces is analogous to disjoint unions of sets, in the sense that the union of the sets of basis vectors from the subspaces are still linearly independent. We can use this idea to prove one direction.

**Problem:** ​Suppose \\(U_1,\dotsc,U_m\\) are finite-dimensional subspaces of \\(V\\) such that \\(U_1+\dots+U_m\\) is a direct sum. Prove that \\(U_1\oplus\dots\oplus U_m\\) is finite-dimensional and
\\[\dim{(U_1\oplus\dots\oplus U_m)}=\dim{U_1}+\dots+\dim{U_m}.\\]

*Solution*: Since the sum is direct, when we write a vector in the sum as a linear combination of all of the basis vectors across all subspaces, no basis vectors collapse (otherwise, we contradict the fact that the sum is direct). So all of these basis vectors are linearly independent, and they span the sum, so they form a basis for the sum and the conclusion follows. \\(\square\\)

It turns out that the converse is also true. To prove this direction, we need to release that when we take the union of the sets of basis vectors for each subspace and we put them all together to form a vector in the sum of subspaces, we are essentially taking vectors in the Cartesian product of the subspaces and mapping them to the sum of the subspaces.

There are few quick things that we can easily verify about the Cartesian product of vector spaces. The first, is that it itself is a vector space. Secondly, the dimension Cartesian product of the vector spaces is the sum of the dimensions of the vector spaces. Both of these are easy to check.

Now, we can prove the other direction. In fact, we will prove both in a much cleaner manner.

**Theorem:** Suppose \\(V\\) is finite-dimensional and \\(U_1,\dotsc,U_m\\) are subspaces of \\(V\\). Then  \\(U_1+\dots+U_m\\) is a direct sum if and only if
\\[\dim{(U_1+\dots+U_m)}=\dim{U_1}+\dots+\dim{U_m}.\\]

*Proof*: Consider the linear transformation \\(\Gamma\colon U_1\times\dots\times U_m\to U_1+\dots+U_m\\) such that it maps \\((u_1,\dotsc,u_m)\mapsto u_1+\dots+u_m\\).

\\(\Gamma\\) is injective if and only if the only vector in its kernel is the zero vector. So there is only one way to write the zero vector in the sum of subspaces, and that is by choosing the zero vector from each subspace. This is a well-known necessary and sufficient condition for a sum to be direct. So \\(\Gamma\\) is injective if and only if the sum of subspaces is direct.

\\(\Gamma\\) is obviously surjective. By the theorem we discussed in the very beginning, regarding the dimensions of the domain and codomain of injective linear transformations and surjective linear transformations (or alternatively, by the rank-nullity theorem), we have that \\(\Gamma\\) is injective iff the dimension of the sum equals the dimension of the Cartesian product.

But the dimension of the Cartesian product is the sum of the dimensions. The result follows. \\(\square\\)