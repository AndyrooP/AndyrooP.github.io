---
layout: post
title: "Matrix Lie Groups"
date: 2021-6-21 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
Here is a problem from Chapter 1 of B. C. Hall. _Lie groups, Lie algebras and Representations_ that I am working on for my REU reading.

**Problem:** A subset \\(E\\) of a matrix Lie group \\(G\\) is called **discrete** if for each \\(A\\) in \\(E\\) there is a neighborhood \\(U\\) of \\(A\\) in \\(G\\) such that \\(U\\) contains no point in \\(E\\) except for \\(A\\). Suppose that \\(G\\) is a path-connected matrix Lie group and \\(N\\) is a discrete normal subgroup of \\(G\\). Show that \\(N\\) is contained in the center of \\(G\\).

_Solution_: To solve this problem, I was first immediately reminded of the map \\(\Phi_X(A)\colon N\to G\\) given by \\(\Phi_X(A)=XAX^{-1}\\) that Hall introduces earlier in the chapter, where we have \\(X\in G\\) and \\(A\in N\\). This map is obviously continuous in both \\(X\\) and \\(A\\) due to the nature of matrix multiplication. More motivation for thinking of this map comes from the fact that \\(\Phi_X\\) actually has its image as a subset of \\(N\\) since \\(N\\) is normal.

I saw that if \\(A\\) was in the center, it must be true that \\(\Phi_X(A)=XX^{-1}A=A\\) for any choice of \\(X\in G\\). Moreover, the converse is true, since \\(XAX^{-1}=A\\) implies \\(XA=AX\\). So it sufficed to show that \\(XAX^{-1}=A\\).

A common construction in path-connected abstract topological spaces is to draw paths connecting a point of interest to an "important point" in the space. I have seen this construction before in algebraic topology, where numerous proofs involving path-lifting requires paths to be drawn from a chosen point in the fiber (which determines the lift), to some other point of interest. In our case, \\(G\\) is a topological group, and an important element of any group is the identity. So we let \\(\lambda_X\colon[0,1]\to G\\) to be the path in \\(G\\) such that \\(\lambda_X(0)=X\\) and \\(\lambda_X(1)=I\\).

​Now define \\(f\colon[0,1]\to G\\) given by
\\[f(t)=\Phi_{\lambda_X(t)}(A).\\]
What I had to show was clear: the function \\(\Phi\\) evaluated at \\(A\\) must be constant along the path \\(\lambda_X(t)\\). In other words, \\(f(t)\\) needed to be the constant function with image \\(A\\).

At this point, I began fiddling with a literal notion of "closeness". One may put the metric induced by the Hilbert-Schmidt (Frobenius) norm on \\(G\\) to turn it into a metric space, and do some \\(\epsilon\\)-\\(\delta\\) calculations to determine that in fact \\(f(t)=A\\) for all \\(t\\). But I later realized that this is not a nice solution, since we are imposing additional (unnecessary) structure on \\(G\\).

It turns out that we can prove the claim entirely topologically. First note that as a composition of continuous functions, \\(f\\) is continuous. Since \\(N\\) is discrete, around each \\(Y\in\mathrm{Im}\ f\\), there exists an open neighborhood \\(U_Y\subseteq G\\) that intersects \\(N\\) only at \\(Y\\). By the continuity of \\(f\\), the sets of the form \\(f^{-1}(U_Y)\\) are open in \\([0,1]\\) (with the subspace topology inherited from \\(\mathbb{R}\\)) and form an open cover of \\([0,1]\\), which is compact by the Heine-Borel theorem. So we can extract a finite subcover.

But the sets in the cover are preimages, so they are pairwise disjoint. The only way to write \\([0,1]\\) as a finite union of pairwise disjoint sets that are open in \\([0,1]\\) is if \\([0,1]\\) is the only (nonempty) set in the union. So one of the preimages is \\([0,1]\\), the entire domain of \\(f\\). That is, there is only one element in the image of \\(f\\). Since \\(f(1)=IAI=A\\), this element is \\(A\\). \\(\square\\)