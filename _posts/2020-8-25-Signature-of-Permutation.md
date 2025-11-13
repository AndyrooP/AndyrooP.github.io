---
layout: post
title: "Signature of a Permutation"
date: 2020-8-25 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
Here is an interesting problem that has surprisingly far-reaching consequences.

Consider a permutation \\(\sigma\colon S\to S'\\) of some list, say \\(S=\\{1,2,\dots,n\\}\\) that maps \\(S\mapsto\\{k_1,k_2,\dots,k_n\\}\\), where \\(k_i\in S\\). Define a _transposition_ to be a permutation that only swaps two elements of the list it acts on. It is clear that every permutation can be decomposed into transpositions. Seriously. It is intuitively obvious.

But if we wanted to be a bit more rigorous, observe that we can give a state to every element \\(j_i\in S\\). Let \\(j_i\\) be _correct_ if \\(j_i=\sigma(j_i)\\), that is, \\(j_i\\) is a fixed point under the permutation. Let \\(j_i\\) be _incorrect_ otherwise.

For every incorrect element in \\(S\\), there must exist another incorrect element in \\(S\\) such that the transposition of the two elements makes the former element correct. So, we can iteratively exclude correct elements, find the unique elements that are in the correct spot of each incorrect element, and perform the transpositions. Since \\(S\\) has finite cardinality, this algorithm terminates, and in fact leaves every element correct.

So any permutation can be decomposed into transpositions. But this does not say anything about the decomposition itself. In fact, there are an infinite number of sequences of transpositions that when composed, yield a given permutation. This is trivial, since we don't have to necessarily stop after the aforementioned algorithm terminates and everything is in the correct spot. You could perform another transposition to "mess things up" and then reverse it, and then continue that an arbitrary number of times.

However, a powerful invariant hides behind all of these decompositions. _For a given permutation, the number of transpositions in any decomposition of that permutation always has the same parity_.

This intuitively makes a lot of sense, though it's not very clear how to prove it. I suppose it would perhaps be possible to do so by performing a case analysis with my states (by considering transpositions of the form "incorrect/correct to correct/incorrect", "correct/correct to incorrect/incorrect", etc.). But this is a bit ugly. There is a much more elegant way, though it is arguably more complicated if you are required to prove the preliminaries from scratch as well.

This _parity_ of a permutation is called its _signature_, and we are concerned with its existence and uniqueness. The signature of a permutation is \\(1\\) when a permutation can only be decomposed into an even number of transpositions and \\(-1\\) otherwise. But there is actually an equivalent definition of signature that we can give with which it is much easier to probe the questions of existence and uniqueness.

Let \\(P_n\\) denote the set of all permutations that act on lists with cardinality \\(n\\). Then the signature is defined as the function
\\[\varsigma\colon P_n\to\\{-1,1\\}\\]
such that \\(\varsigma(\sigma_1\circ\sigma_2)=\varsigma(\sigma_1)\varsigma(\sigma_2)\\) for all \\(\sigma_1,\sigma_2\in P_n\\) and \\(\varsigma(\tau)=-1\\) if \\(\tau\\) is a transposition. The signature is usually denoted by "sgn", but due to MathJax limitations, I will denote it with \\(\varsigma\\).

We need to show that this definition is equivalent to our parity definition, and also that the signature exists and is unique (using this definition). Showing the equivalence of the definitions is trivial. Since the signature of the composition is the product of the signatures, and the signature of a transposition is \\(-1\\), we must have that the signature is \\(\varsigma(\sigma)=(-1)^{T(\sigma)}\\), where \\(T(\sigma)\\) gives the number of transpositions in any one of the decompositions of \\(\sigma\\). Now we must prove that this function exists and is unique.

Proving existence is the hard part. For any permutation \\(\sigma\in P_n\\), define the _permutation matrix_ \\(M_{\sigma}\\) as the matrix that maps
\\[M\_{\sigma}\vec{e}\_i=\vec{e}\_{\sigma(i)},\\]
where \\(\vec{e}\_i\\) is just a standard basis vector in \\(\mathbb{R}^n\\). It follows that \\(M\_{\sigma}\\) is some \\(n\times n\\) matrix which only 0's and 1's, which I won't compute explicitly (though it isn't hard to).

It is easy to see for \\(\sigma_1,\sigma_2\in P_n\\), we have \\(M_{\sigma_1\circ\sigma_2}=M_{\sigma_1}M_{\sigma_2}\\). Here comes our leap of faith. Define
\\[\varsigma(\sigma)=\det{M_{\sigma}}.\\]
This fits our first property, since the determinant of a product is the product of the determinants! Furthermore, the second property is satisfied as well, since one can easily show that for some transposition \\(\tau\\), the matrix \\(M_{\tau}\\) is found by transposing two columns in the identity matrix (and so the determinant is negated, due to the antisymmetry of the determinant – this argument is sometimes phrased in terms of the determinant of an elementary matrix representing the transposition of two columns). Hence, the function \\(\varsigma\\) exists.

But, if \\(\varsigma\\), a function, exists, then each element in the domain can only map to one element in the codomain, so it is also unique. By equivalence of definitions, this means that the number of transpositions of every decomposition of \\(\sigma\\) into transpositions always has the same parity!

The signature ends up being quite important for various definitions in the theory of forms in vector calculus, such as the wedge product. All of this from just viewing a permutation as a series of transpositions.