---
layout: post
title: "What is the shape of water rotating in a bucket?"
date: 2020-5-8 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
Here is an interesting problem that was walked through in my homework for physics class (PHYS 4B at UCSD).

**Problem:** Consider water (or some inviscid fluid) rotating in a large bucket with constant angular velocity, \\(\omega\\) (about the axis through the center of the bucket). What shape does the surface of the water take?

The solution was unfortunately given away by the structure of the problem in the homework (it was split up into parts). Nonetheless, I think that it is a very cool problem and worth expositing. The key idea is Bernoulli's principle.

*Solution*: We leave the lab frame and enter a frame, which we will call \\(S\\) that rotates along with the water in the bucket. Observe that this frame is non-inertial, since it accelerates with respect to the lab frame.

So we perceive fictitious forces in \\(S\\). Importantly, a packet of water at a constant distance from the axis will stay at that constant distance and the centrifugal force it feels is actually the centripetal force that keeps it in uniform circular motion.

This means that the force vector in our frame has a clean form in cylindrical coordinates, \\((r,\theta,z)\\). Let the axis of rotation hit the floor of the bucket at the origin, \\((0,0,0)\\). The force on a packet of water is thus given by
\\[\vec{F}=mr\omega^2\hat{e}_r-mgz\hat{e}_z.\\]
That is, the net force felt in this frame is a combination of the centrifugal force and weight. Since the centrifugal force is the centripetal force, which proportional to the mass, we can apply the equivalence principle. That is, the laws of physics do not change in our frame, as long as we account for an extra fictitious force that is proportional to mass.

One may question why we take the radial component of our force (which is the centrifugal force here) to be *positive*. The reason is because in \\(S\\), each packet of water is stationary! So it does not have an inward radially-directed centripetal force. The centrifugal force happens to actually be directed *outward* (but still radially). This occurs to yield equilibrium in \\(S\\). A free body diagram will be balanced with the outward centrifugal force, weight, and contact force normal to the surface. I won't say more here, because seeing things this way actually leads to a *simpler* solution of the problem which is not what I am trying to demonstrate at the moment!

Going back to our problem, now that we have a force function, we can come up with a potential \\(\varphi\\) such that \\(\vec{F}=-m\vec{\nabla}\varphi\\) (observe the similarities with other forms of potential, such as electric potential, namely that we keep mass out of \\(\varphi\\) as we would keep charge out of the electric field). This is just a standard exercise in basic calculus. We have that
\\[\frac{\partial\varphi}{\partial r}=-r\omega^2\Rightarrow\varphi=\int{-r\omega^2\textrm{ d}r}=-\frac{1}{2}\omega^2r^2+A(\theta,z),\\]
\\[\frac{\partial\varphi}{\partial z}=g\Rightarrow\varphi=\int{g\textrm{ d}z}=gz+B(r,\theta).\\]
From equating these two expressions for \\(\varphi\\), we have that \\(A(\theta,z)=gz+C\\) and \\(B(r,\theta)=-\frac{1}{2}\omega^2r^2+C\\). Putting everything together, we have
\\[\varphi(r,z)=gz-\frac{1}{2}\omega^2r^2+C,\\]
for some constant \\(C\\). The choice of \\(C\\) is irrelevant, since a potential by itself is meaningless – only a potential *difference* has an interpretation. WLOG, take the potential at the origin to be zero, so that \\(C=0\\).

Next, consider a tube along a radial direction on the surface of the water. By Bernoulli's principle in the lab frame, we have that
\\[p+\frac{1}{2}\rho v_{\textrm{tube}}^2+\rho gz=C,\\]
where \\(p\\) is the pressure, \\(\rho\\) is the density of water, \\(v_{\textrm{tube}}\\) is the speed of flow in the tube, and \\(C\\) is some constant. But for \\(v_{\textrm{tube}}\\) to be nonzero, a fluid packet must have some radial component of velocity (again, remember that we are now in the lab frame). But this is not true since the water is just rotating in the bucket! So Bernoulli's principle reduces to the statement
\\[p+\rho gz=C.\\]
Now, let us add and subtract \\(\frac{1}{2}\rho\omega^2r^2\\) to the LHS of the above equation. We obtain
\\[p+\frac{1}{2}\rho\omega^2r^2+\rho gz-\frac{1}{2}\rho\omega^2 r^2=C.\\]
Now \\(\omega r=v\\), the true speed of any packet of water rotating in the bucket. And the last to terms are just \\(\rho\varphi\\)! So we obtain a modified form of Bernoulli's principle:
\\[p+\frac{1}{2}\rho v^2+\rho\varphi=C.\\]
This statement could also have been derived by understanding what exactly Bernoulli's principle asserts. In particular, it states that the sum of pressure, kinetic energy density, and potential energy density is an invariant. We could have just modified the potential energy density term by introducing \\(\varphi\\).

More implicitly, what's going on here is that we are using the equivalence principle. That is, we are saying that the combination of the true gravitational force and the centrifugal force is indistinguishable from a very strange modified gravitational force in \\(S\\). Furthermore, since in \\(S\\) we have \\(v=0\\), our modified Bernoulli's principle now reads
\\[p+\rho\varphi=C.\\]
Now we take a point on the surface, say \\((0,\theta_0,z_0)\\). For elegance, let this be the point on the surface that is also on the axis of rotation. For any point on the surface, we must have that \\(p=p_0\\), the atmospheric pressure! In particular, we have
\\[p_0+\rho\varphi(0,z_0)=C.\\]
And now we are done. Because the surface of the water is just the locus of points where the pressure is equal to atmospheric pressure. In particular, we will have
\\[p_0+\rho\varphi(r,z)=p_0+\rho\varphi(0,z_0).\\]
Rearranging this gives
\\[\varphi(r,z)=\varphi(0,z_0)\Rightarrow z=\frac{1}{2g}\omega^2r^2+\frac{1}{g}\varphi(0,z_0).\\]
This, in fact, fits the cylindrical form of a paraboloid. \\(\square\\)

It is interesting to note that the solution is entirely determined by energy conservation and the equivalence principle. But any problem that can be solved with energy conservation can also be solved directly by Newton's laws. So it is in fact possible to find a simpler solution, which I mentioned before. The idea there is to simply note that an observer in \\(S\\) would see that the system is in static equilibrium. I'll leave that solution to the reader.