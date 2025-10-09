---
layout: post
title: "Hiatus and Current (haha) happenings"
date: 2020-11-8 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
As you can tell, there has been a bit of a hiatus. Haven't really been productive (beyond just working on my classes) in the meanwhile. But I'm back now! I suppose this will be a bit of a meta post, followed by some electromagnetic theory.

First of all, I'm working on a research project (along with principal investigator <a href="https://cass.ucsd.edu/index.php/postdocs:Tsiegert" target="_blank">Dr. Thomas Siegert</a>). The project pertains the impact of small solar system bodies (SSSBs) on gamma ray data from <a href="https://en.wikipedia.org/wiki/INTEGRAL" target="_blank">INTEGRAL</a>. I'll probably talk a bit more about this once I move farther into the project and have a better grasp of things.

I'm also giving a lecture on linear algebra at the San Diego Math Circle (SDMC). I plan on drawing inspiration from some of the stuff that I've exposited on here. In particular, I really want to show the students that linear algebra is a lot more than just Euclidean vectors and solving simultaneous linear equations. That lecture will be happening this Saturday (11/14).

Some of the heuristic arguments in physics rub me in the wrong way (due to the lack of mathematical rigor), but I cannot deny the importance of being able to reason quickly with heuristics in physics (and in general, using ad hoc methods that aren't entirely rigorous is, in my opinion, both _natural and fine_ in the path to a more rigorous solution). Here are some examples.

The electric field and potential are related by \\(\vec{E}=-\nabla\phi\\). It follows that the divergence of the electric field is related to the Laplacian of the potential:
\\[\nabla\cdot\vec{E}=-\nabla^2\phi.\\]
Gauss' law tells us that \\(\int_{S}{\vec{E}\cdot\mathrm{d}\vec{a}}=\frac{Q}{\epsilon_0}=\frac{1}{\epsilon_0}\int_{V}{\rho\ \mathrm{d}v}\\), where \\(\rho\\) is the charge density. However, Gauss' theorem says that the integral of the flux over the surface is equal to the integral of the divergence in the volume. Equating the integrands gives us \\(\nabla\cdot\vec{E}=\frac{\rho}{\epsilon_0}\\), hence
\\[\nabla^2\phi=-\frac{\rho}{\epsilon_0}.\\]
​But when \\(\rho=0\\), as is the case in empty space where there are no charges, the potential function must satisfy Laplace's equation
\\[\nabla^2\phi=0.\\]
This equation is pretty important, and there is quite a bit of theory behind it, as it not only pops up here, but in other areas (such as heat transfer). I don't even remember much of the basic theory we learned about it in MATH 110, but there is one property of functions that satisfy Laplace's equation (called _harmonic functions_) that is relevant here.

**Theorem:** Let \\(f\colon U\to\mathbb{R}\\) be a harmonic function over the set \\(U\subset\mathbb{R}^3\\). Then, the average value of \\(f\\) over any sphere contained in \\(U\\) is equal to the value of \\(f\\) at the center of that sphere. An analogous result holds in two dimensions as well, if \\(U\subset\mathbb{R}^2\\) and we replace spheres with circles.

_Proof (sketch)_​: I know of two ways of thinking about this. Ironically, neither of them are entirely rigorous. One of them is something you'd expect to encounter from an applied math class (like MATH 110), and the other is a physical argument that applies just to electric potentials (provided in Purcell).

The applied math-y way is to consider the Taylor expansions of \\(f\\) incremented and decremented by \\(h\\) in each variable, one at a time. Then, you add each pair (for instance, \\(f(x+h,y,z)+f(x-h,y,z)\\)). This eliminates mixed partials (at least the lower-order ones). Then, you can isolate the repeated second partial derivative terms (partial with respect to \\(x\\) and then \\(x\\), etc.) in each pair-sum. Plugging these expressions into Laplace's equation, one finds that neglecting the higher-order terms, the value of \\(f\\) is equal to the to the average of the values of function at the points that are incremented and decremented by \\(h\\) away from the center, in each direction. Heuristically, we can extend this to _every_ direction in a full sphere around the center point.

​Physically, we consider a point charge \\(P\\) with charge \\(Q\\) and a sphere \\(\Omega\\) that has a charge \\(q\\) distributed uniformly over it, such that the center of \\(\Omega\\) is a distance \\(R\\) from \\(P\\). We can compute how much work it takes to construct this configuration, in two different ways.

The first way is to note that due to the shell theorems, outside of \\(\Omega\\), it is electromagnetically indistinguishable from a point charge with charge \\(q\\) at its center. Hence, the work required to assemble the configuration is the same as the work required to bring two point charges together (or more precisely, bring \\(P\\) in from infinity). This is simply \\(\frac{Qq}{4\pi\epsilon_0R}\\).

On the other hand, instead of bringing \\(P\\) in from infinity, we can bring \\(\Omega\\) in from infinity. Then, the work done must be equal to the _average potential_ over \\(\Omega\\) times the total charge of \\(\Omega\\). But clearly, the work done doesn't change from us thinking about it this way! So we still have a work of \\(\frac{Qq}{4\pi\epsilon_0R}\\). This means that the average potential over \\(\Omega\\) is simply \\(\frac{q}{4\pi\epsilon_0R}\\), which is precisely the potential at the center of \\(\Omega\\) due to \\(P\\). So the electric potential function satisfies the theorem in empty space that does not contain charges, where there is only one point charge in the universe. Superposition gives the general result for arbitrary charge distributions in the universe.

A simple corollary of this result is that no harmonic function can have local extrema (or at least, extrema will be on the boundary of the domain over which the function _is_ harmonic). This leads itself naturally into _Earnshaw's theorem_, which states that there exists no configuration that provides a stable equilibrium for a point charge. To see this, observe that if there was a point in space where there was a stable equilibrium, the potential there must be a local minimum, a contradiction. Alternatively, the electric field at such a point would have to have a negative divergence. Gauss' law then says a negative must exist at that point, contradicting our assumption that we were considering empty space.

There's quite a bit more to talk about, but I'll end it here for now. I've procrastinated quite a bit and I need to catch up on other stuff!