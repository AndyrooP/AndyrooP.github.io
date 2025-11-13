---
layout: post
title: "Fixing Childhood Misconceptions: Bump Functions and Divergent Evolution"
date: 2021-6-24 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
Two days ago, I had an interesting interaction with some other students in my REU that destroyed two misconceptions I have had in analysis for a long time.

First, we introduce the idea of a bump function. Let \\(M\\) be a smooth manifold with \\(A\subseteq U\subseteq M\\), where \\(A\\) is closed and \\(U\\) is open. We define a **bump function for \\(A\\) supported in \\(U\\)** to be a continuous function \\(\psi\colon M\to\mathbb{R}\\) with \\(0\leq\psi\leq1\\) on \\(M\\), \\(\psi=1\\) on \\(A\\), and \\(\mathrm{supp}\ \psi\subseteq U\\).

So far so good. It is not a particular surprise that such a function exists. We only require that \\(\psi\\) be continuous. Here is where my intuition had failed me for years up to this point: _smooth bump functions exist​_! This was a complete shock to me. I was not familiar with any smooth functions that were constant in some neighborhood, and non-constant elsewhere. Moreover, I have thought about this scenario many times before and concluded that it ought to be impossible. I figured if a function was of class \\(C^{\infty}\\), then it could not be constant (so that its derivatives of all orders vanished) and then suddenly get kicked and start moving. I believed that for such a "kick" to occur, one of the functions derivatives must be discontinuous, staying at zero in some neighborhood before suddenly jumping to some nonzero value.

​Alas, I was wrong. Smooth bump functions do exist. This follows from the existence of smooth partitions of unity. Most of the technical work that goes into proving that smooth bump functions exist is actually hidden under the rug of proving that smooth partitions of unity exist. But taking that for granted, we note that \\(U\\) and \\(M\setminus A\\) form an open cover of \\(M\\). Then, one may find a smooth partition of unity \\(\\{\psi,\lambda\\}\\) subordinate to this cover. By definition, \\(\lambda\\) vanishes on \\(A\\), so \\(1=\psi+\lambda=\psi\\) on \\(A\\). Indeed, this \\(\psi\\) is the desired bump function!

​Having crushed one of my childhood misconceptions, another was crushed the other day when I saw the following proposition in Lee's _Introduction to Smooth Manifolds_.

Proposition: Let \\(M\\) be a smooth manifold with or without boundary, \\(p\in M\\), \\(v\in T_pM\\). If \\(f,g\in C^{\infty}(M)\\) agree on some neighborhood of \\(p\\), then \\(vf=vg\\).

The statement of this theorem is not particularly relevant, but the hypothesis immediately caught my eye. Why is it stipulated that \\(f\\) and \\(g\\) agree just on some neighborhood of \\(p\\)? I had always figured that the evolution of smooth functions were determined by their behavior in any neighborhood (similar to how continuous functions are determined by their behavior on dense subsets). The motivation here was the uniqueness of solutions to differential equations and dynamical systems. Once one describes a global relationship between a a function and its derivatives, and an initial condition, the evolution of the function past the starting point is determined. I believed that if we strengthen the agreement between two functions to occur not at a single point, but an entire neighborhood, and that both functions were \\(C^{\infty}\\), then the evolutions of the functions beyond on the neighborhood must also agree.

In other words, I did not understand why the proposition said that \\(f\\) and \\(g\\) agree on some neighborhood, because I thought that that occurs precisely when they agree _everywhere_.

Alas, this is also wrong. Upon discussing this with some other students at my REU, I found the counterexample I was looking for. Using our previous notation, if one considers \\(g=\psi f\\), where \\(\psi\\) is a bump function, both functions agree in any neighborhood contained in \\(A\\) by construction, but are very free to disagree outside of \\(A\\)! Somehow, it seems that bump functions allow us to construct strange functions whose derivatives fail to propagate local information globally, _even though the functions are infinitely smooth_! This observation is further strengthened by the fact that bump functions are actually used in the proof of the proposition written above (and the proposition itself is a statement about how tangent vectors do not care about global behavior—they only care about local behavior).

No contradiction is reached with my intuition stemming from unique solutions to differential equations. After all, having a relationship between a function and its derivatives that holds everywhere is quite a strong condition, and it's not any surprise that unique evolution is forced in that scenario.

After a little bit of digging, I found the gap in my knowledge. The <a href="https://en.wikipedia.org/wiki/Identity_theorem" target="_blank">identity theorem</a> states that analytic functions that agree on some neighborhood must agree everywhere. So it seems that I have stumbled upon a crucial qualitative difference between analytic functions and smooth functions. In particular, analyticity is a strong enough condition for local behavior (at least in a neighborhood) to propagate globally, while smoothness is not. Obviously, any concrete examples that I attempted to think of were analytic.

My intuition is still grappling with this. But it's good to know that I was wrong for so long.