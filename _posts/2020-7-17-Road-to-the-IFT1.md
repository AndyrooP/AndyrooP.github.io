---
layout: post
title: "Road to the Implicit Function Theorem: Part 1 – Lipschitz Ratios and Newton's Method"
date: 2020-7-17 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
Back in April, I discussed the basics of manifolds here, and mentioned that I might begin a blog series on the foundations of the implicit function theorem. I start the journey here.

I have thought long and hard about whether I should keep this exploration in the blog, or perhaps flesh it out and push it to the main mathematics page. Ultimately, I have decided to keep it here for a few reasons.
​

- I will not be proving anything. I will only be outlining sketches of proofs and discussing the main ideas.
- The discussion will be entirely theoretical, with no applications to external problems. This does not preclude simple examples that will be used to demonstrate certain concepts in action, (not being creatively applied as they would be in a real *problem*).
- This is meant to follow my personal exploration of these concepts. So I will be informal and talk about half-baked ideas that may be dead ends, or assorted topics that are only tangentially related.


The material I am referencing and learning from is *Vector Calculus, Linear Algebra, and Differential Forms*​, by Hubbard. This is the primary textbook for the MATH 31-series at UC San Diego.

Newton's method is a central technique in numerical analysis, and the single-variable form is often introduced in single-variable calculus. The generalization to multiple variables is pretty direct. We wish to find roots of a differentiable function \\(f\colon U\to\mathbb{R}^n\\), where \\(U\\) is an open subset of \\(\mathbb{R}^n\\). We make a guess at the root, say \\(\vec{a}_0\\). Now, we determine the root of the linearization of \\(f\\) at \\(\vec{a}_0\\). This comes out to finding the solution \\(\vec{a}_1\\) to the equation
\\[f(\vec{a}_0)+\[Df(\vec{a}_0)\](\vec{a}_1 - \vec{a}_0)=\vec{0}.\\]
If everything goes well, the solution \\(\vec{a}_1\\) is unique. Furthermore, if things are good, we can iterate this process, and the sequence \\(i\mapsto\vec{a}_i\\) converges to a root of \\(f\\).

There are a few things to notice here. The first thing to notice is that for unique \\(\\vec{a}_i\\) to exist at each step, the linear equation defining \\(\vec{a}_i\\) must have a unique solution:

$$[Df(\vec{a}_{i-1})](\vec{a}_i-\vec{a}_{i-1})=-f(\vec{a}_{i-1}).$$

For this to be the case, \\([Df]\\) needs to be a square matrix. This explains why the domain and codomain of \\(f\\) must have the same dimension. Furthermore, we must have that \\([Df(\vec{a}_i)]\\) is always invertible. These are two obvious conditions that must be met for Newton's method to converge to a root.

There are some other intuitive conditions that we could impose that would ensure that Newton's method converges. Obviously, our initial guess should be somewhat close to a root in the sense that the function evaluated at that point is almost 0. That is, \\(\|f(\vec{a}_0)\|\\) should be small. Furthermore, the derivative should be large (in magnitude). This way, we have a large change in \\(f\\) from where we start, and have so we have a larger likelihood of approaching a root from that initial guess. Finally, the derivative of \\(f\\) must not change too much. If it did, then it does not matter if we have a large change in \\(f\\) where we start – that change in \\(f\\) itself can drastically change if we move a bit away from \\(f\\) if the derivative changes too much.

We have already made it precise what we mean by \\(\vec{a}_0\\) should be "close" to being a root (\\(\|f(\vec{a}_0)\|\\) should be small). Now we make our third point more precise. A natural way to measure the rate of change of the derivative is by taking the second derivative. But perhaps even more natural than that is to take the linearization of the second derivative and bound the change in the image of two points under the derivative. To do this, we introduce the idea of a *Lipschitz condition*.

​Let \\(U\\) be an open subset of \\(\mathbb{R}^n\\) and let \\(f\colon U\to\mathbb{R}^n\\). Then \\(f\\) satisfies a Lipschitz condition on \\(V\subset U\\) with Lipschitz ratio \\(M\\) if for all \\(\vec{x},\vec{y}\in V\\),
\\[|f(\vec{x})-f(\vec{y})|\leq M|\vec{x}-\vec{y}|.\\]
This makes pretty good sense. In fact, contraction mappings, which we have discussed earlier, satisfy a Lipschitz condition, by definition. In particular, they are Lipschitz functions with \\(0<M<1\\). Another observation we can quickly make is that any Lipschitz function must also be continuous. What about differentiability? It turns out that deducing anything about differentiability from a Lipschitz condition is nontrivial, but indeed, *Rademacher's theorem* states that if \\(f\\) is Lipschitz on \\(V\\), then it is also differentiable almost everywhere on \\(V\\).

Where the function happens to be differentiable and Lipschitz, the Lipschitz condition immediately places a bound on the derivative. In fact, as we will see, the converse is also true. A bounded derivative implies Lipschitz.

But before we proceed further, we need to clarify something. We need the derivative to be Lipschitz. But the derivative is a matrix, and it is unclear how the norm of a matrix is defined. For our purposes, we use the *Frobenius norm* which is defined as just an extension of the normal vector norm. For a matrix \\(A\\), it is defined as
\\[|A|^2=\sum_{A}{a_{i,j}^2}.\\]
So now it makes sense for us to say that a "derivative is bounded". What we really mean is that the Frobenius norm of the Jacobian is bounded.

Computing Lipschitz ratios is somewhat of an art, like integrating elementary functions. They require a bit of fiddling with inequalities, and typically we establish the region over which we wish to verify that the function is Lipschitz to be some open ball around the origin, so we force some inequalities ourselves. As it turns out, there is a more systematic way to do this – using the fact that a bounded derivative implies Lipschitz. Since we are bounding the *derivative* in the first place (i.e. trying to establish that the derivative is Lipschitz), we will actually be working with second partial derivatives.

Let \\(U\subset\mathbb{R}^n\\) be an open ball and \\(f\colon U\to\mathbb{R}^n\\) be a \\(C^2\\) mapping. If
\\[\left|\frac{\partial f_i}{\partial x_k\partial x_j}(\vec{x})\right|\leq c_{i,j,k}\\]
for any \\(\vec{x}\in U\\) and for all triples \\(1\leq i,j,k\leq n\\), then the derivative of \\(f\\) is Lipschitz with Lipschitz ratio
\\[M=\sqrt{\sum_{1\leq i,j,k\leq n}{c_{i,j,k}^2}}\\]
over \\(U\\).

The cost of using a systematic approach such as this is that the Lipschitz ratios that we obtain aren't quite as strong as we could get from fiddling with inequalities ourselves. But the main utility is that using the second derivatives to find a Lipschitz ratio for the derivative is quite straightforward. The proof of this statement is quite straightforward. It is a simple application of the mean value theorem.

Now that we have the machinery to quantify any possible condition that would ensure that Newton's method converges, we can state Kantorovich's theorem. This theorem gives a sufficient (but not necessary) condition for Newton's method to converge. As such, it is an enormously important theoretical result. Without it, no one would *really​* be justified in using Newton's method! We will discuss the theorem in the next post.