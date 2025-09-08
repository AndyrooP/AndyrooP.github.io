---
layout: post
title: "Classical physics is pretty"
date: 2019-6-25 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

It's a shame that quantum and relativistic corrections are necessary. Though perhaps it's self-entitled of me to wish that the universe would be simple enough for me to understand it.

It turns out that current flows in such a way that power loss in resistors is minimized in parallel. This claim comes from problem 2 from a pset <a href="https://ocw.mit.edu/courses/18-02sc-multivariable-calculus-fall-2010/2.-partial-derivatives/part-c-lagrange-multipliers-and-constrained-differentials/problem-set-6/" target="_blank">here</a>.

Consider two resistors in parallel. The current into a terminal is \\(I\\). Let the current the resistors be \\(I_1\\) and \\(I_2\\), and let the resistances be \\(R_1\\) and \\(R_2\\), respectively. Then by conservation of charge:

$$I=I_1+I_2,$$

and since power dissipated through a resistor is \\(I^2R\\), we have a total power loss of:

$$P(I_1,I_2)=I_1^2R_1+I_2^2R_2.$$

Now we have a simple optimization problem. We must minimize the function above subject to the constraint \\(S(I_1,I_2)=I_1+I_2=I\\). We proceed with Lagrange multipliers:

$$\nabla P=\lambda\nabla S\Rightarrow\left<2I_1R_1,2I_2R_2\right>=\left<\lambda,\lambda\right>.$$

From this, we immediately obtain:

$$I_1R_1=I_2R_2,$$

which if Ohm's law holds, is simply \\(V\\), the potential difference across the resistors! This physically makes sense. Potential difference is constant over resistors in parallel since all of the resistors of coinciding terminals and potential difference is path-independent. The calculation above easily generalizes to an arbitrary number of resistors.

I am awaiting a response on StackExchange for a greater physical insight into *why* currents arrange themselves such that power dissipation is minimized. This seems to be a manifestation of a <a href="https://en.wikipedia.org/wiki/Path_of_least_resistance" target="_blank">common theme</a> throughout physics.

For instance, Fermat's principle from optics states that light will always choose a path that minimizes travel time. This is an interesting principle, but it is actually due to the Huygens principle, in which waves are framed as propagating by new *wavelets* emanating from each wavefront. I am simply wondering if there is a similar underlying principle behind why currents travel so that power dissipation is minimized in parallel resistors.