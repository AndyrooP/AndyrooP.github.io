---
layout: post
title: "Capacitance"
date: 2019-3-26 10:00:00
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

We start by considering two parallel plate conductors. Suppose that one of them has a charge density of \\(\sigma\\), and that the other has a charge density of \\(-\sigma\\). Gauss' law implies an electric field of \\(\frac{\sigma}{\varepsilon_0}\\).

Now Gauss' law was perfectly satisfying, but I couldn't help but wonder where I went wrong in reasoning that each parallel plate, acting as a conductor, contributes an electric field of \\(\frac{\sigma}{\varepsilon_0}\\) over the gap between the two plates, resulting in a net electric field of \\(\frac{2\sigma}{\varepsilon_0}\\). I had already seen many interpretations of the correct result coming from considering each plate to be a sheet of charge (which would cause each plate to contribute \\(\frac{\sigma}{2\varepsilon_0}\\) by Gauss' law, yielding the correct answer). Why was it incorrect to consider each plate *conductor* to produce electric fields in accordance with *conductors* instead of sheets of charges?

I took the issue to Stack Exchange. My question was marked as a duplicate, and I found that someone else had asked the same question and received <a href="https://physics.stackexchange.com/questions/65191/what-is-the-electric-field-in-a-parallel-plate-capacitor/65194#65194" target="_blank">a beautifully explained response</a> from user David Z. Here is the key run down.

We can consider infinitely thin plates. In this case, the conductors behave as sheets of charge, since there is not *thickness* to the plate where there could possibly be an internal electric field to violate electrostatic equilibrium.

If we were adamant on the condition that our plates must have thickness, we can note that charges migrate to the *inner* surface (where *inner* denotes the side of the plate that faces the gap between the plates), and to achieve electrostatic equilibrium in the system, an identical charge distribution (though with opposite polarity of course) forms on the inner surface of the other plate. The key insight is that the symmetric charge distribution formation on the inner surface of the second plate is a direct consequence of the electric field induced by the first plate, hence *​it does not contribute its own independent electric field*. The electric field in the gap is hence simply that obtained by considering one of the plates to be a conductor, which is \\(\frac{\sigma}{\varepsilon_0}\\).

Anyway, this system of charged parallel plate conductors is a capacitor. It functions as a device to store electrostatic potential energy. To find exactly how much energy is stored in a capacitor, we consider the work it takes to separate both plates from each other to a separation of \\(h\\).

​We mustn't apply a force of \\(EA\sigma\\). This is because we must consider the *average* electric field of one of the conductors. Since it is zero on the outer side and \\(E\\) on the inner side, the correct force is \\(\frac{1}{2}EA\sigma\\). Therefore, the work done is:
\\[U=\frac{1}{2}EA\sigma h\\]
But notice that \\(Ah\\) is the volume enclosed, hence by rearranging the equation, we can obtain the energy density of a capacitor:
\\[u=\frac{1}{2}E\sigma=\frac{1}{2}\varepsilon_0 E^2\\]
By using the definition of capacitance, \\(C=\frac{Q}{V}\\), and the fact that \\(V=Eh\\) in this scenario, we obtain the common formulas for the energy stored in a capacitor:
\\[U=\frac{1}{2}CV^2=\frac{1}{2}QV=\frac{Q^2}{2C}\\]
*University Physics* was kind enough to point out to me that the last expression above demonstrates that a capacitor behaves analogously to a spring in storing potential energy, where the reciprocal of capacitance is analogous to the spring constant and charge is analogous to the stretch from equilibrium of the spring.

Simple calculations show that in a circuit, capacitance enjoys additive properties that are opposite to those of resistance.

I'll try to wrap up this post soon. In our discussion so far, we assumed that the gap between the plates of a capacitor was a vacuum. In fact, it is possible to put some other material in this gap. Doing so will form a substantial dielectric for sufficiently strong electric fields (resulting from sufficiently high charge densities). The dielectric actually *increases* the capacitance of the capacitor by a factor of \\(\kappa\\). This is why in the real world, capacitor plates (which are rolled up in cylinders to maximize surface area for a given volume) are separated by some insulating material. Not only does this prevent electrical breakdown and discharge through contact, but it also increases the capacitance of the capacitor!

Also, the permittivity \\(\varepsilon\\) is defined by \\(\varepsilon=\kappa\varepsilon_0\\). This explains why \\(\varepsilon_0\\) is called the *permittivity of free space*. Because the dielectric constant is \\(1\\) in a vacuum!

There are many, many more results that are direct corollaries of what I've discussed here. But these are the essential pieces that I have learned thus far. Good night!