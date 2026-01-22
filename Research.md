---
layout: work
title: Research
permalink: /research
---

#### Papers
1. ***Weak convergence of spectral shift functions revisited*** with <a href="https://carsonconnard.xyz/" target="_blank">Carson Connard</a>, Benjamin Ingimarson, and <a href="https://sites.google.com/mocs.utc.edu/rogernicholshomepage/home" target="_blank">Roger Nichols</a>; November 2022; *Pure and Applied Functional Analysis*​, Volume 9(4), 2024, pages 1023–1051. [arXiv: <a href="https://arxiv.org/abs/2211.14970" target="_blank">2211.14970</a>]
2. ***Topological Properties of Almost Abelian Groups*** with <a href="https://www.z-avetisyan.com/" target="_blank">Zhirayr Avetisyan</a>, Oderico-Benjamin Buran, and Lisa Reed; August 2023. [arXiv: <a href="https://arxiv.org/abs/2308.08059" target="_blank">2308.08059</a>]

#### Expository
1. ***Algebraic Topology*** (in progress) [<a href="/myassets/docs/ResearchDocs/AlgTop.pdf" target="_blank">PDF</a>]
1. ***Hodge Theory and Complex Algebraic Geometry*** (in progress) [<a href="/myassets/docs/ResearchDocs/HodgeTheory.pdf" target="_blank">PDF</a>]
1. ***​​Chern Classes and Lines on a Cubic Surface***​, UC San Diego Honors Thesis, June 2023, updated 11/7/2023 [<a href="/myassets/docs/ResearchDocs/HonorsThesisV5.pdf" target="_blank">PDF</a>]
1. ***Set Theory and Cardinality***, Chapel Hill Math Circle, November 22, 2025 [<a href="/myassets/docs/ResearchDocs/SetTheoryandCardinality.pdf" target="_blank">PDF</a>]

See <a href="https://anpaul.weebly.com/archives.html" target="_blank">here</a> for stuff I wrote mostly in high school.

#### Open Questions
These are open (to me) questions that are in the back of my head. They represent the various gaps in my knowledge that I feel I should fill in. Some of them are precisely stated and others are more vague. If you have good answers to these questions, please let me know!

1. Vakil 11.4.7 is an algebraic generalization of <a href="https://en.wikipedia.org/wiki/Liouville%27s_theorem_(complex_analysis)#On_compact_Riemann_surfaces" target="_blank">Liouville's theorem</a>. He states that Grothendieck's coherence theorem (Vakil 18.9.1) is a further generalization. What is the coherence theorem really saying and how is it a generalization? ~~Also, how is the assumption that $k$ is algebraically closed being used in the proof?~~
  - $k$ being algebraically closed is what allows us to identify the closed points of $\mathbb{A}_k^1$ with the constants from $k$ (via the weak Nullstellensatz).
1. What is the exact relationship between <a href="https://en.wikipedia.org/wiki/Hartogs%27s_extension_theorem" target="_blank">Hartogs' extension theorem</a> in several complex variables, and the algebraic Hartogs' lemma (Vakil 13.5.19)? Is the curve-to-projective extension theorem (Vakil 15.3.1) related to these?
1. What are spectral sequences and how do they work?
1. Griffith's & Harris goes about defining the curvature matrix of a connection $D$ on a complex vector bundle $E\to M$ as follows. For sections $\psi\in\mathcal{A}^p(U)$ and $\zeta\in\mathcal{A}^0(E)(U)$, we enforce the Leibniz rule
\\[D(\psi\wedge\zeta)=d\psi\otimes\zeta+(-1)^p\psi\wedge D\zeta.\\]
Then a calculation shows that the operator $D^2\colon\mathcal{A}^0(E)\to\mathcal{A}^2(E)$ is $C^{\infty}$-linear: if $\sigma$ is a section of $E$ and $f$ is a $C^{\infty}$-function, we will have $D^2(f\cdot\sigma)=f D^2\sigma$. From here onward, I don't understand what follows. Griffith's & Harris states that it follows from this that $D^2\colon\mathcal{A}^0(E)\to\mathcal{A}^2(E)$ is induced by a bundle map $E\to\bigwedge^2T^{\*}\otimes E$, or in other words, $D^2$ corresponds to a global section $\Theta$ of the bundle
\\[\bigwedge^2T^{\*}\otimes\operatorname{Hom}{(E,E)}\cong\bigwedge^2T^{\*}\otimes(E^{\*}\otimes E).\\]
Then given a frame $e$ for $E$, $\Theta\in\mathcal{A}^2(E^{\*}\otimes E)$ can be represented by a matrix $\Theta_e$ of $2$-forms. What does $C^{\infty}$-linearity imply that $D^2$ is "induced by a bundle map" and in what way is this induced? How does this then correspond to a section of the above bundle?
1. What does it mean to perform a homotopy on an almost complex structure?


<!--
1. Traditionally in "algebraic" algebraic geometry, given a Weil divisor $D$, the corresponding sheaf $\mathcal{O}_X(D)$ is defined by

$$\Gamma(U,\mathcal{O}_X(D)):=\left\{ t\in K(X)^{\times}\colon\operatorname{div}{|_Ut}+D|_U\geq 0\right\}\cup\{0\}.$$

This is the definition provided in, for instance, 15.4.6.1 of Vakil. Vakil goes on to state (Exercise 15.4.J) that when $D$ is a locally principal divisor, the sheaf $\mathcal{O}_X(D)$ is a line bundle. On the other hand, in complex algebraic geometry (for example, Griffiths & Harris) we might define the the line bundle associated to a divisor $D$
-->

