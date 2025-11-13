---
layout: post
title: "Basic Convergence Theorems of the Lebesgue Integral"
date: 2021-12-20 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
One of the greatest advantages of the Lebesgue integral over the Riemann integral is its good behavior under limits. There are three big theorems in measure theory that demonstrate this feature of the Lebesgue integral. The first of these is the monotone convergence theorem.

**Monotone Convergence Theorem:** If \\(\\{f_n\\}\\) is a convergent sequence in \\(L^+\\) such that \\(f_j\leq f_{j+1}\\) for all \\(j\\), then \\(\int{\lim_{n\to\infty}{f_n}}=\lim_{n\to\infty}{\int{f_n}}\\).

_Proof_: Suppose that the measure space we are working in is \\((X,\mathscr{M},\mu)\\). First, note that \\(\\{f_n\\}\\) is an increasing sequence of functions, so \\(\\{\int{f_n}\\}\\) is an increasing sequence of real numbers. Thus, \\(\lim_{n\to\infty}{\int{f_n}}\\) exists, at least in the extended real numbers. Put \\(f=\lim_{n\to\infty}{f}\\). Secondly, since \\(\int{f_n}\leq\int{f}\\) for all \\(n\\), we also have that \\(\lim_{n\to\infty}{\int{f_n}}\leq\int{f}\\). It remains to prove the reverse inequality.

​Pick a simple function \\(\phi\\) such that \\(0\leq\phi\leq f\\). Let \\(\alpha\in(0,1)\\) be arbitrary. Define \\(E_n=\\{x\in X\colon f_n(x)\geq \alpha\phi(x)\\}\\). Since the \\(f_n\\) are increasing, \\(f_n(x)\geq\alpha\phi(x)\\) will imply \\(f_m(x)\geq\alpha\phi(x)\\) for all \\(m\geq n\\). Hence, the \\(E_n\\) are an increasing sequence of sets: \\(E_1\subseteq E_2\subseteq \dots\\). Fix \\(x\in X\\). The sequence \\(\\{f_n(x)\\}\\) is an increasing sequence of real numbers converging to \\(f(x)\\). Hence, there exists some \\(N\\) such that for all \\(n>N\\) we have that \\(0\leq f(x)-f_n(x)\leq f(x)-\alpha\phi(x)\\). So for all \\(n>N\\) we have \\(f_n(x)\geq\alpha\phi(x)\\) so \\(x\in E_n\\). In particular, \\(X=\bigcup_{n=1}^{\infty}{E_n}\\).

By the definitions, we have
\\[\int{f_n}\geq\int_{E_n}{f_n}\geq\alpha\int_{E_n}{\phi}.\\]
Hence,
\\[\lim_{n\to\infty}{\int{f_n}}\geq\alpha\lim_{n\to\infty}{\int_{E_n}{\phi}}.\\]
Recall that for \\(E\in\mathscr{M}\\), the map \\(E\mapsto\int_{E}{\phi}\\) is itself a measure, say \\(\nu\\). Since the \\(E_n\\) are increasing, by continuity from below on the measure \\(\nu\\), we have that
\\[\lim_{n\to\infty}{\int_{E_n}{\phi}}=\int_{\bigcup_{n=1}^{\infty}{E_n}}{\phi},\\]
so our inequality becomes
\\[\lim_{n\to\infty}{\int{f_n}}\geq\alpha\int{\phi}.\\]
Since this holds for \\(\alpha\in(0,1)\\), it will hold for \\(\alpha=1\\). Hence,
\\[\lim_{n\to\infty}{\int{f_n}}\geq\int{\phi}.\\]
Finally, taking the supremum over all simple functions \\(\phi\leq f\\), we obtain the desired inequality
\\[\lim_{n\to\infty}{\int{f_n}}\geq\int{f}.\\]
\\(\square\\)

The definition of \\(\int{f}\\) requires us to consider the supremum of the set of integrals of simple functions that do not exceed \\(f\\), but the monotone convergence theorem tells us that we may instead compute the integral as \\(\int{f}=\lim_{n\to\infty}{\int{\phi_n}}\\), where \\(\\{\phi_n\\}\\) is an increasing sequence of simple functions that converges to \\(f\\) almost everywhere​. It is a standard first result in measure theory that such sequences of simple functions exist. The monotone convergence theorem allows us to interchange integrals with limits when the limit is taken on a sequence of increasing functions.

But if the dream is to be able to interchange the integral with a limit for all sequences of functions, we must prepare to be disappointed. The classic pathology is the sequence of mass functions \\(f_n=\chi_{(n,n+1)}\\). Of course, the sequence \\(\\{f_n\\}\\) converges pointwise to the function \\(f(x)=0\\), but \\(\int{f_n}=1\\) for all \\(n\\), so we clearly cannot interchange the limit and the integral in this scenario. The issue here is that even though there is convergence to a nice function, there is a non-negligible mass that preserved in every function of the sequence. A related example is given by \\(f_n=n\chi_{\left(0,\frac{1}{n}\right)}\\). Once again, the integral of each function in the sequence is \\(1\\), but the function converges pointwise to \\(0\\). Again, the issue is that there is a non-negligible mass that is preserved in every function of the sequence.

A reasonable objection may be the following. In both examples above, the convergence is pointwise but not uniform, so perhaps the limit and integral fail to be interchangeable because the convergence is not strong enough. This is also wrong: consider \\(f_n=\frac{1}{n}\chi_{(0,n)}\\). In this case, \\(f_n\to 0\\) not just pointwise, but uniformly. Nonetheless, \\(\int{f_n}=1\\) for every \\(n\\), so the limit and integral cannot be interchanged. It turns out that the relationship between the standard modes of convergence and the limiting behavior of integrals is a subtle one which I will talk about in the future. So the failures that we have demonstrated are truly an inherent limitation of the Lebesgue integral, not a weakness of the form of convergence. Nonetheless, there is something we _can_ say when we have no condition on the sequence of functions (not even the condition that they converge to something).

**Fatou's Lemma:** If \\(\\{f_n\\}\\) is any sequence in \\(L^+\\), then
\\[\int{\liminf{f_n}}\leq\liminf{\int{f_n}}.\\]

​_Proof_: For every \\(k\geq1\\) and \\(j\geq k\\) we have that \\(\inf_{n\geq k}{f_n}\leq f_j\\) and thus \\(\int{\inf_{n\geq k}{f_n}}\leq\int{f_j}\\). This is preserved when we take the infimum of the left:
\\[\int{\inf_{n\geq k}{f_n}}\leq\inf_{j\geq k}{\int{f_j}}.\\]
For every \\(k\\), let \\(g_k=\inf_{n\geq k}{f_n}\\) and consider the sequence of functions \\(\\{g_k\\}\\). Clearly,\\(g_1\leq g_2\leq\dots\\). So by the monotone convergence theorem, we have that
\\[\int{\liminf_{n\to\infty}{f_n}}=\int{\lim_{k\to\infty}{g_k}}=\lim_{k\to\infty}{\int{g_k}}\leq\lim_{k\to\infty}{\inf_{j\geq k}{\int{f_j}}}=\liminf_{n\to\infty}{\int{f_n}}.\\]
\\(\square\\)

Fatou's lemma can be used to derive another proof of the monotone convergence theorem.

_Second Proof (Monotone Convergence Theorem)_: Recall that in the first proof, it was immediate that \\(\lim_{n\to\infty}{\int{f_n}}\leq\int{f}\\), so it suffices to show the reverse inequality. But this is immediate by Fatou's lemma. In particular, if a limit exists, it is equal to the limit infimum, so \\(f=\liminf_{n\to\infty}{f_n}\\) and \\(\lim_{n\to\infty}{\int{f_n}}=\liminf_{n\to\infty}{\int{f_n}}\\). \\(\square\\)

​Fatou's lemma has weak hypotheses but is a weak result. Moreover, one may ask: what about sequences in \\(L^1\\)? So far we have only been dealing with sequences in \\(L^+\\). The dominated convergence theorem is the main result that we use in practice, and is arguably one of the most important results in measure theory.

**Dominated Convergence Theorem:** ​Let \\(\\{f_n\\}\\) be a convergent sequence in \\(L^1\\) such that there exists \\(g\in L^1\\) with \\(\|f\_n\|\leq g\\) almost everywhere for all \\(n\\), then \\(\lim_{n\to\infty}{f_n}\in L^1\\) and \\(\int{\lim_{n\to\infty}{f_n}}=\lim_{n\to\infty}{\int{f_n}}\\).

_Proof​_: Let \\(\lim_{n\to\infty}{f_n}=f\\) almost everywhere. Some standard results show that \\(f\\) is measurable. Since \\(|f|\leq g\in L^1\\), we must have that \\(f\in L^1\\). Suppose that the \\(f_n\\) are real-valued. By the hypothesis, we have that \\(g+f_n\geq0\\) and \\(g-f_n\geq0\\) almost everywhere.  Now we can compute
\\[\begin{split}
\int{g}+\int{f}&=\int{g+f}\\\\\
&=\int{\left(g+\lim_{n\to\infty}{f_n}\right)}\\\\\
&=\int{\liminf_{n\to\infty}{\left(g+f_n\right)}}\\\\\
&\leq\liminf_{n\to\infty}{\int{(g+f_n)}}\\\\\
&=\int{g}+\liminf_{n\to\infty}{\int{f_n}},
\end{split}\\]
where we invoke Fatou's lemma to obtain the inequality. Similarly,
\\[\begin{split}
\int{g}-\int{f}&=\int{g-f}\\\\\
&=\int{\left(g-\lim_{n\to\infty}{f_n}\right)}\\\\\
&=\int{\liminf_{n\to\infty}{\left(g-f_n\right)}}\\\\\
&\leq\liminf_{n\to\infty}{\int{(g-f_n)}}\\\\\
&=\int{g}-\limsup_{n\to\infty}{\int{f_n}}.
\end{split}\\]
Rearranging the two inequalities gives us \\(\liminf_{n\to\infty}{\int{f_n}}\geq\int{f}\\) and \\(\int{f}\geq\limsup_{n\to\infty}{\int{f_n}}\\). So it follows that
\\[\int{f}=\lim_{n\to\infty}{\int{f_n}}.\\]
In general, if the \\(f_n\\) are not real-valued, we can break it up into the positive and negative parts of its real and imaginary parts and apply the same procedure as above to arrive at the conclusion. \\(\square\\)
​
The dominated convergence theorem shows up in the proofs of many other foundational theorems of measure theory, as it accepts a mild hypothesis and permits one to interchange a limit and integral in exchange, which is a very useful operation. To get some more feel for the three big convergence theorems, we will interpret them in a special case.

Consider the measure space \\((\mathbb{N},\mathscr{P}(\mathbb{N}),\mu)\\) where \\(\mu\\) is the counting measure. Let \\(\\{f_n\\}\\) be an arbitrary sequence in \\(L^+\\) (with respect to this measure space). What does this really mean? For each \\(n\\), we may construct the family of simple functions \\(\\{\phi_m^n\\}\\) as follows. First, define
\\[\phi_1^n=f_n(1)\chi_{f_n^{-1}(f_n(1))}.\\]
Define,
\\[A_m=\mathbb{N}\setminus\bigcup_{j=1}^{m}{f_n^{-1}(f_n(k))}.\\]
For \\(m>1\\), if \\(A_m=\varnothing\\), set \\(\phi_m^n=\phi_{m-1}^n\\). Otherwise, let \\(k_m\\) be the minimal element of \\(A_m\\) and set
\\[\phi_m^n=\phi_{m-1}^n+f_n(k_m)\chi_{f_n^{-1}(f_n(k_m))}.\\]
Observe that by construction, \\(\lim_{m\to\infty}{\phi_m^n}=f_n\\) everywhere, and \\(m\\), \\(\phi_1^n\leq\phi_2^n\leq\dots\leq f_n\\). So by the monotone convergence theorem,
\\[\int{f_n}=\lim_{m\to\infty}{\int{\phi_m^n}}=\sum_{k=1}^{\infty}{f_n(k)},\\]
where the sum comes from the construction of \\(\phi_m^n\\) and the fact that \\(\mu\\) is the counting measure. So we may interpret \\(\int{f_n}\\) as simply the sum of its values. In particular, there is a correspondence between functions in \\(L^+\\) with respect to our measure space and sequences of numbers in \\([0,\infty]\\). Let \\(\\{S_n\\}\\) be a family of such sequences, where
\\[S_n=s_{n,1},s_{n,2}\dots\\]
and let \\(\\{f_n\\}\\) be the family of functions in \\(L^+\\) such that \\(f_n(k)=s_{n,k}\\). Let \\(T\\) be the sequence given by
\\[T=t_1,t_2,\dots\\]
where \\(t_k=\liminf_{n\to\infty}{s_{n,k}}\\). Corresponding to this sequence is the function \\(\liminf_{n\to\infty}{f_n}\\). Hence, Fatou's lemma tells us that
\\[\sum_{k=1}^{\infty}{\liminf_{n\to\infty}{s_{n,k}}}\leq\liminf_{n\to\infty}\sum_{k=1}^{\infty}{s_{n,k}}.\\]
​Now, let us further insist that the sequences \\(S_n\\) are such that for each \\(k\\), \\(s_{1,k}\leq s_{2,k}\leq\dots\\). Of course, for each \\(k\\), \\(\lim_{n\to\infty}{s_{n,k}}\\) is guaranteed to exist due to the compactness of \\([0,\infty]\\). Then by the monotone convergence theorem,
\\[\lim_{n\to\infty}{\sum_{k=1}^{\infty}{s_{n,k}}}=\sum_{k=1}^{\infty}{\lim_{n\to\infty}{s_{n,k}}}.\\]
​We need some extra work to interpret the dominated convergence theorem in this context. Integrals of functions \\(\mathbb{N}\to\mathbb{C}\\) can still be interpreted as the infinite sum of their values by splitting up the function into the positive and negative parts of its real and imaginary parts and applying our work above on \\(L^+\\) functions, and using the linearity of the integral. Suppose that \\(\\{f_n\\}\\) is a sequence of functions \\(\mathbb{N}\to\mathbb{C}\\) in \\(L^1\\) such that \\(f_n\to f\\) almost everywhere and there is a nonnegative \\(g\in L^1\\) such that \\(g\geq|f_n|\\) almost everywhere for each \\(n\\). Note that the functions \\(|f_n|\\) are in \\(L^+\\), and by our previous interpretation of such functions, they correspond to sequences of numbers from \\([0,\infty]\\). Hence, the condition \\(f_n\in L^1\\) is equivalent to
\\[\sum_{k=1}^{\infty}{|f_n(k)|}<\infty.\\]
Observe that in the measure space \\((\mathbb{N},\mathscr{P}(\mathbb{N}),\mu)\\), the only null set is the empty set. Hence, convergence almost everywhere is equivalent to convergence everywhere in this context. In particular, for each \\(k\\), \\(f(k)=\lim_{n\to\infty}{f_n(k)}\\). Moreover, notice that \\(g\\) is in \\(L^+\\), so
\\[\sum_{k=1}^{\infty}{|f_n(k)|}\leq\sum_{k=1}^{\infty}{g(k)}<\infty.\\]
So the interpretation is the following. Let \\(\\{S_n\\}\\) be a family of sequences of complex numbers
\\[S_n=s_{n,1},s_{n,2},\dots,\\]
such that for each \\(k\\), \\(\lim_{n\to\infty}{s_{n,k}}\\) exists, and there exists a sequence of nonnegative real numbers \\(s_1,s_2,\dots\\) with
\\[\sum_{k=1}^{\infty}{|s_{n,k}|}\leq\sum_{k=1}^{\infty}{s_k}<\infty,\\]
for each \\(n\\). By the dominated convergence theorem,
\\[\sum_{k=1}^{\infty}{\lim_{n\to\infty}{s_{n,k}}}=\lim_{n\to\infty}{\sum_{k=1}^{\infty}{s_{n,k}}},\\]
and moreover,
\\[\sum_{k=1}^{\infty}{\lim_{n\to\infty}{|s_{n,k}|}}<\infty.\\]