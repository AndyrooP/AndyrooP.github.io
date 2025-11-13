---
layout: post
title: "Coherence is not a good notion in smooth geometry"
date: 2025-9-6 12:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Here is an interesting story about a key difference between smooth (differential) geometry and analytic/algebraic geometry. It is taken from Exercise 6.4.11 of Vakil (note that the exercise shares the same name as this blog post), which itself descends from Brian Conrad.

**Theorem:** Let \\(\mathcal{O}\_{\mathbb{R}}\\) be the sheaf of \\(C^{\infty}\\) functions on the \\(\mathbb{R}\\) equipped with its usual differentiable structure. Then \\(\mathcal{O}\_{\mathbb{R}}\\) is not a coherent \\(\mathcal{O}\_{\mathbb{R}}\\)-module.

This is a surprising result that indicates the nicest possible structure sheaf in differentiable geometry does not interact well with the notion of coherence, thereby making coherence an uninteresting notion in differential geometry. To prove this fact, we will show that \\(\mathcal{O}\_{\mathbb{R}}\\) fails to have a coherent stalk at \\(0\\) (in fact our argument can be adapted to show that all of the stalks are not coherent). For this strategy to work, we need to know that the stalks of a coherent sheaf are coherent, so let us take the time to prove this.

**Lemma:** Let \\((X,\mathcal{O}\_X)\\) be a ringed space and let \\(\mathcal{F}\\) be a coherent sheaf on \\(X\\). Then for every \\(p\in X\\), the stalk \\(\mathcal{F}\_p\\) is a coherent \\(\mathcal{O}\_{X,p}\\)-module.

_Proof of Lemma_: The heart of this lemma is that the stalkification functor is exact. Fix a point \\(p\in X\\). There are two things to check, namely that \\(\mathcal{F}\_p\\) is finitely generated as an \\(\mathcal{O}\_{X,p}\\)-module and that for any natural number \\(n\\) and morphism \\(\mathcal{O}\_{X,p}^{\oplus n}\to\mathcal{F}\_p\\) of \\(\mathcal{O}\_{X,p}\\)-modules, the kernel is finitely generated.

Since we are working on a ringed space, we will need to use the <a href="https://en.wikipedia.org/wiki/Coherent_sheaf" target="_blank">most general definition of coherence</a>. For the first fact, we note that since \\(\mathcal{F}\\) is coherent, it is of finite type. Hence, there exists a neighborhood \\(U\\) of \\(p\\) and a natural number \\(n\\) for which there is an exact sequence:
\\[\mathcal{O}\_{X}^{\oplus n}\|\_U\longrightarrow\mathcal{F}\|\_U\longrightarrow 0.\\]
But stalkfication is exact, so by taking stalks at \\(p\\) we obtain the exact sequence
\\[\mathcal{O}\_{X,p}^{\oplus n}\longrightarrow\mathcal{F}\_p\longrightarrow 0.\\]
Hence, \\(\mathcal{F}\_p\\) is finitely generated as an \\(\mathcal{O}\_{X,p}\\)-module.

Now we move to the second thing to be proven. Let \\(\Phi\_p\colon\mathcal{O}\_{X,p}^{\oplus n}\to\mathcal{F}\_p\\) be a morphism of \\(\mathcal{O}\_{X,p}\\)-modules. Of course, the generators of \\(\mathcal{O}\_{X,p}^{\oplus n}\\) arise from the germ of the global section \\(1\in\mathcal{O}\_X(X)\\). Let these generators be \\((e\_1)\_p,(e\_2)\_p,\dots,(e\_n)\_p\\). Suppose \\(\Phi\_p((e\_i)\_p)=\overline{(U\_i,f\_i)}\\) for each \\(i\\), where we explicitly write down representatives for each germ in \\(\mathcal{F}\_p\\) (in particular, \\(f\_i\in\mathcal{F}(U\_i)\\)). Let \\(V=\bigcap\_{i=1}^{n}{U\_i}\\). This is nonempty since it contains \\(p\\) and open since \\(n\\) is finite, but most importantly, \\(f\_i\|\_V\\) is a genuine section of \\(\mathcal{F}\\) over \\(V\\) for each \\(i\\). Hence we may define a map \\(\Psi\colon\mathcal{O}\_X^{\oplus n}\|\_V\to\mathcal{F}\|\_V\\) by \\(\Psi\_W(e\_i\|\_W)=f\|\_W\\) for every open \\(W\subseteq V\\).

With this definition, it is clear that \\(\Psi\\) induces the map \\(\Phi\_p\\) on the stalks at \\(p\\). The point of all of this is that we have promoted the map \\(\Phi\_p\\) on stalks to a map of sheaves at least in some neighborhood of \\(p\\). Since \\(\mathcal{F}\\) is coherent, we know that \\(\ker{\Psi}\\) is of finite type. So there is some neighborhood \\(W\\) of \\(p\\) and natural number \\(m\\) such that we have an exact sequence
\\[\mathcal{O}\_X^{\oplus m}\|\_W\longrightarrow\ker{\Psi}\longrightarrow 0.\\]
Since stalkification is exact, we have the exact sequence:
\\[\mathcal{O}\_{X,p}^{\oplus m}\longrightarrow(\ker{\Psi})\_p\longrightarrow 0.\\]
Once again, since stalkification is exact, we have \\((\ker{\Psi})\_p\cong\ker{(\Psi\_p)}\cong\ker{\Phi\_p}\\). Hence, we have an exact sequence
\\[\mathcal{O}\_{X,p}^{\oplus m}\longrightarrow\ker{\Phi\_p}\longrightarrow 0,\\]
establishing that \\(\ker{\Phi\_p}\\) is finitely generated. This completes the proof of the lemma. \\(\square\\)

With this lemma in hand, we can now discuss the proof of the theorem as shown in Exercise 6.4.11.

_Proof of Theorem_: The stalk \\(\mathcal{O}\_{\mathbb{R},0}\\) is a local ring whose maximal ideal \\(\mathfrak{m}\\) consists of germs of smooth functions vanishing at \\(0\\). Pick a germ in this maximal ideal defined by a function defined on \\((-\epsilon,\epsilon)\\) for some \\(\epsilon>0\\). Then by the fundamental theorem of calculus, for every \\(x\in(-\epsilon,\epsilon)\\) we have
\\[f(x)=f(0)+\int\_{0}^{t}{f'(u)\, \mathrm{d}u}=\int\_{0}^{x}{f'(u)\, \mathrm{d}u}=x\int\_{0}^{1}{f(xv)\, \mathrm{d}v}.\\]
Also by the <a href="https://en.wikipedia.org/wiki/Leibniz_integral_rule" target="_blank">Leibniz integral rule</a>, since \\(f\\) is \\(C^{\infty}\\), so is the function \\(\int\_{0}^{1}{f(xv)\, \mathrm{d}v}\\). Therefore, \\(\mathfrak{m}\subseteq \langle x\_0\rangle\\). The reverse inclusion is obviously true, so \\(\mathfrak{m}=\langle x\_0\rangle\\).

Now consider the function
\\[\phi(x)=\begin{cases}
0 & x\leq 0\\\\\
e^{-1/x^2} & x>0.
\end{cases}\\]
Notice that \\(\phi(x)\\) is smooth even at \\(0\\), since both of its pieces are smooth and the limits of their derivatives of all orders agree as we approach \\(0\\). Consider the map \\(\Phi\_0\colon\mathcal{O}\_{\mathbb{R},0}\to\mathcal{O}\_{\mathbb{R},0}\\) given by multiplying germs by the germ \\(\phi\_0\\). Note that \\(\ker{\Phi\_0}\\) is nontrivial, since it includes functions such as \\(\phi(-x)\\) which vanishes for all positive \\(x\\). In general, the kernel contains functions that vanish on \\([0,\epsilon)\\) for any \\(\epsilon>0\\). In particular, everything in \\(\ker{\Phi\_0}\\) vanishes at \\(0\\) so \\(\ker{\Phi\_0}\subseteq\mathfrak{m}\\) and in fact our calculation above with the fundamental theorem of calculus shows that every element of \\(\ker{\Phi\_0}\\) can be written as \\(x\psi(x)\\) for some \\(\psi(x)\in\ker{\Phi\_0}\\). Therefore, \\(\ker{\Phi\_0}\subseteq\mathfrak{m}\ker{\Phi\_0}\\). The reverse inclusion is also immediately true so in fact \\(\ker{\Phi\_0}=\mathfrak{m}\ker{\Phi\_0}\\). But since \\(\ker{\Phi\_0}\\) is nontrivial, it follows from <a href="https://en.wikipedia.org/wiki/Nakayama%27s_lemma" target="_blank">Nakayama's lemma</a> that \\(\ker{\Phi\_0}\\) must be infinitely generated as an \\(\mathcal{O}\_{\mathbb{R},0}\\)-module! Therefore, the stalk \\(\mathcal{O}\_{\mathbb{R},0}\\) is not coherent, and we conclude by the lemma above that the sheaf \\(\mathcal{O}\_{\mathbb{R}}\\) is not coherent over itself. \\(\square\\)

This is a very interesting result as first of all, it shows some of the geometric ramifications of Nakayama's lemma. As the Wikipedia article notes, there are geometric interpretations of Nakayama's lemma which allow us to connect fibers of coherent sheaves with local sections in some neighborhood. Hence for a coherent sheaf, the behavior of the sheaf at a point strongly controls the behavior in a neighborhood of that point.

Moreover, this result gives some appreciation for the distinction between the smooth and analytic settings. The argument above works because of the existence of the function \\(\phi\\). This function \\(\phi\\) is infinitely differentiable _but it is not analytic_ since analytic functions must obey the <a href="https://en.wikipedia.org/wiki/Identity_theorem" target="_blank">identity principle</a>. If an analytic function vanishes on an open set then it must in fact vanish everywhere. For this reason, analytic functions are much more "rigid"; enough so that while the sheaf of \\(C^{\infty}\\) functions on a differentiable manifold is not generally coherent as we have shown above, the sheaf of holomorphic functions on a complex manifold is. This is <a href="https://en.wikipedia.org/wiki/Oka_coherence_theorem" target="_blank">Oka's coherence theorem</a>, which is famously a deep and difficult result in complex analytic geometry.