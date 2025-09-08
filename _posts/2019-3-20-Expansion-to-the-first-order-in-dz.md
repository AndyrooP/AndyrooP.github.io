---
layout: post
title: "Expansion to the first order in \\(\\mathrm{d}z\\)"
date: 2019-3-20 10:00:00
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

This is from David Morin's *Introductory Classical Mechanics*.

The problem is to consider a rope of linear mass density \\(\rho\\) and length \\(\ell\\) lying on an inclined plane with an initial angle of \\(0\\) which is then raised to some angle \\(\theta\\). Suppose a coefficient of friction, \\(\mu\\) exists between the plane and the rope, and that the topmost end of the rope is nailed to the plane. What is the tension at the top of the rope?

Morin approaches this by first parameterizing the position along the rope as \\(z=x\sec{\theta}=y\csc{\theta}\\), where the plane is oriented with the bottommost point of the plane (also the bottom end of the rope) at the origin, and the plane extends into the first quadrant.

Next, he considers an infinitesimal segment of the rope, from \\(z\\) to \\(z+\textrm{d}z\\). The upward forces on this segment are \\(T(z+\textrm{d}z)\\), the tension on the upper end of the rope, and \\(F_f(z)\textrm{d}z\\), the force of friction on the segment, where the function \\(F_f(z)\\) gives the force of friction per unit length for a given \\(z\\) coordinate. The downward forces on the segment are \\(T(z)\\), the tension on the lower end of the rope, and \\(\rho g\sin{\theta}\textrm{ d}z\\), the weight down the plane of the segment. Since the rope is at rest everywhere:
\\[T(z+\textrm{d}z)+F_f(z)\textrm{d}z=T(z)+\rho g\sin{\theta}\textrm{ d}z\\]
Morin then states: "Expanding this to first order in \\(\textrm{d}z\\) gives"
\\[\frac{\textrm{d}T}{\textrm{d}z}=\rho g\sin{\theta}-F_f(z)\\]
Now I don't know what it means to expand something to first order in some differential unit, but I can arrive where Morin did by rearranging the first equation as:
\\[\frac{T(z+\textrm{d}z)-T(z)}{\textrm{d}z}=\rho g\sin{\theta}-F_f(z)\\]
And then observing that the LHS is equivalent to the limit definition of the derivative:
\\[\frac{T(z+\textrm{d}z)-T(z)}{\textrm{d}z}=\lim_{h\rightarrow 0}{\frac{T(z+h)-T(z)}{h}}=\frac{\textrm{d}T}{\textrm{d}z}\\]
Is that what it means to "expand to the first order"?

​Anyway, Morin continues by asserting that if there is to be any tension at all in the top portion of the rope (or any portion of the rope for that matter), we must have \\(\tan{\theta}>\mu\\) (which is a well-known, easily obtainable result). In that case, frictional force is maximized:
\\[F_f(z)=\rho g\mu\cos{\theta}\\]
The result follows upon integration:
\\[\int{\textrm{d}T}=\int{\rho g\sin{\theta}-\rho g\mu\cos{\theta}\textrm{ d}z}\\]
Using the initial condition \\(T(0)=0\\), we conclude:
\\[T(\ell)=\rho g(y_0-\mu x_0)\\]
Where \\((x_0,y_0)\\) is the location of the top end of the rope.

I went about this problem in an almost correct way. I forgot to account for the fact that the tension in the bit of rope *above* each infinitesimal segment pulled *upward* on that segment. :(. Hey, now I know better.

Yes, solutions to problems from *Introductory Classical Mechanics* will be up soon. I will present solutions to problems that I have solved myself correctly (so not this one). Otherwise, I'm effectively regurgitating the solutions manual.