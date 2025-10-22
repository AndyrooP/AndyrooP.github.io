---
layout: post
title: "Complex and Fréchet Differentiability"
date: 2021-12-18 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
Complex differentiability is a famously strong condition, especially when it occurs in a neighborhood of every point in the domain. One longstanding question that I had was about the qualitative difference between the complex derivative and the standard <a href="https://en.wikipedia.org/wiki/Fr%C3%A9chet_derivative" target="_blank">Fréchet derivative</a> from multivariable calculus.

To be precise, suppose that \\(f\colon\mathbb{R}^2\to\mathbb{R}^2\\) is a function given by \\(f(x,y)=(u(x,y),v(x,y))\\). Let \\(h\colon\mathbb{C}\to\mathbb{R}^2\\) be the canonical identification \\(h(x+yi)=(x,y)\\), and let \\(g\colon\mathbb{C}\to\mathbb{C}\\) be given by \\(g=h^{-1}\circ f\circ h\\). Observe that there is a natural correspondence between \\(f\\) and \\(g\\), and we very well could have defined \\(g\\) first and then \\(f\\) (formally, \\(f\\) and \\(g\\) are related by conjugation which is an <a href="https://en.wikipedia.org/wiki/Inner_automorphism" target="_blank">inner automorphism</a>). What is the relationship between the Fréchet differentiability of \\(f\\) and the complex differentiability of \\(g\\)? When both derivatives exist, what is the relationship between the Fréchet derivative \\(Df\\) and the complex derivative \\(g'\\)?

First, suppose \\(g\\) is complex differentiable at \\(z\in\mathbb{C}\\). Then,
\\[g'(z)=\lim_{w\to0}{\frac{g(z+w)-g(z)}{w}}\\]
exists. Pick \\(\epsilon>0\\). By the above, there exists \\(\delta>0\\) such that \\(0<|w|<\delta\\) implies that
\\[\left|\frac{g(z+w)-g(z)}{w}-g'(z)\right|=\frac{|g(z+w)-g(z)-wg'(z)|}{|w|}<\epsilon.\\]
In other words, we have that
\\[\lim_{w\to0}{\frac{|g(z+w)-g(z)-wg'(z)|}{|w|}}=0.\\]
Suppose \\(\alpha=\mathrm{Re}\ g'(z)\\), \\(\beta=\mathrm{Im}\ g'(z)\\), \\(x=\mathrm{Re}\ w\\), and \\(y=\mathrm{Im}\ w\\). Now, if we define the linear operator
\\[A=\begin{bmatrix}
\alpha & -\beta\\\\\
\beta & \alpha
\end{bmatrix},\\]
we have that
\\[wg'(z)=(x+yi)(\alpha+\beta i)=\alpha x-\beta y+(\alpha y+\beta x)i=h^{-1}\left(\begin{bmatrix}
\alpha & -\beta\\\\\
\beta & \alpha
\end{bmatrix}\begin{bmatrix}
x\\\\\
y
\end{bmatrix}\right)=(h^{-1}\circ A\circ h)(w).\\]
Observe that since \\(\mathbb{C}\\) and \\(\mathbb{R}^2\\) are isomorphic as metric spaces, distances between corresponding points are the same irrespective of which space we decide to compute them in. In particular, if \\(t=h(w)\\) and \\(s=h(z)\\), then
\\[\frac{|g(z+w)-g(z)-wg'(z)|}{|w|}=\frac{|(h\circ g)(z+w)-(h\circ g)(z)-h(wg'(z))|}{|h(w)|}.\\]
But by our work above, \\(h(wg'(z))=(A\circ h)(w)\\), so
\\[\frac{|g(z+w)-g(z)-wg'(z)|}{|w|}=\frac{|(h\circ g)(z+w)-(h\circ g)(z)-(A\circ h)(w)|}{|h(w)|}=\frac{|f(s+t)-f(s)-At|}{|t|}.\\]
Taking \\(t\to\vec{0}\\) is equivalent to taking \\(w\to0\\), hence
\\[\lim_{t\to\vec{0}}{\frac{|f(s+t)-f(s)-At|}{|t|}}=\lim_{w\to0}{\frac{|g(z+w)-g(z)-wg'(z)|}{|w|}}=0.\\]
So \\(f\\) is Fréchet differentiable at \\(h(z)\\), with Fréchet derivative \\(A\\) which has a simple relationship with \\(g'(z)\\).

On the other hand, if we start with the assumption that \\(f\\) is Fréchet differentiable, it is not necessarily true that \\(g\\) is complex differentiable. For example, suppose \\(f(x,y)=x^2+y^2\\), so \\(g(z)=|z|^2\\). Obviously, \\(f\\) is Fréchet differentiable everywhere. But, suppose that \\(z_0=a+bi\\) is a nonzero complex number. Then, we can compute the limit
\\[L_1=\lim_{x\to0}{\frac{g(z+x)-g(z)}{x}},\\]
when \\(x\\) is restricted to the real numbers. Along this path, we compute
\\[\begin{split}
L_1&=\lim_{x\to0}{\frac{(a-x)^2+b^2-a^2-b^2}{x}}\\\\\
&=\lim_{x\to0}{\frac{x^2-2ax}{x}}\\\\\
&=\lim_{x\to0}{x-2a}\\\\\
&=-2a.
\end{split}\\]
On the other hand, we can take a limit along the imaginary axis. Define,
\\[L_2=\lim_{y\to0}{\frac{g(z+yi)-g(z)}{yi}}.\\]
Then,
\\[\begin{split}
L_2&=\lim_{y\to0}{\frac{a^2+(b-y)^2-a^2-b^2}{yi}}\\\\\
&=\lim_{y\to0}{\frac{y^2-2by}{yi}}\\\\\
&=\frac{1}{i}\lim_{y\to0}{y-2b}\\\\\
&=2bi.
\end{split}\\]
Of course, since \\(z_0\neq0\\), we have that \\(L_1\neq L_2\\), so \\(g'(z_0)\\) fails to exist. The complex derivative of \\(g\\) only exists at \\(0\\), where it is easily checked that \\(g'(0)=0\\).

So the complex differentiability of \\(g\\) is stronger than the Fréchet differentiability of \\(f\\). This leads to the next natural question: what do we need in addition to the Fréchet differentiability of \\(f\\) to ensure the complex differentiability of \\(g\\)? One can easily see that our argument that the complex differentiability of \\(g\\) implies the Fréchet differentiability of \\(f\\) works in reverse. In particular, if the Fréchet derivative of \\(f\\) is of the form given by \\(A\\), then the complex derivative of \\(g\\) exists at the point in question where it is \\(\alpha+\beta i\\).

We can say more if we assume continuity of the complex derivative of \\(g\\) and the partial derivatives of \\(u\\) and \\(v\\). Suppose \\(g'\\) exists in an open connected set and is continuous. One may compute the complex derivative of \\(g\\) in two different ways. Just as we did above, if one computes the limit along the real axis, it is immediate that
\\[g'(z)=\frac{\partial u}{\partial x}(h(z))+i\frac{\partial v}{\partial x}(h(z)).\\]
On the other hand, computing the limit along the imaginary axis gives us
\\[g'(z)=\frac{\partial v}{\partial y}(h(z))-i\frac{\partial u}{\partial y}(h(z)).\\]
Equating these two expressions for \\(g'(z)\\) yields the *Cauchy-Riemann equations*
\\[\frac{\partial u}{\partial x}=\frac{\partial v}{\partial y}\qquad \frac{\partial u}{\partial y}=-\frac{\partial v}{\partial x}.\\]
These equations are actually precisely the extra nudge that Fréchet differentiability needs to translate into complex differentiability (with the assumptions of continuity we mentioned before). To see this, suppose that \\(u\\) and \\(v\\) satisfy the Cauchy-Riemann equations in an open connected set \\(G\\) and that they have continuous partial derivatives. Fix \\(z=x+yi\in G\\). Since \\(G\\) is open, there exists \\(r>0\\) such that \\(B_r(z)\subseteq G\\). Let \\(h=s+ti\\) such that \\(|h|<r\\). Then, by the mean value theorem, there exists \\(s_1,t_1\in\mathbb{R}\\) such that \\(|s_1|<|s|\\), \\(|t_1|<|t|\\), and
\\[u(x+s,y+t)-u(x,y+t)=u_x(x+s_1,y+t)s\\]
\\[u(x,y+t)-u(x,y)=u_y(x,y+t_1)t.\\]
Now, we may define
​\\[\varphi(s,t)=[u(x+s,y+t)-u(x,y)]-[u_x(x,y)s+u_y(x,y)t].\\]
Notice that
\\[\begin{split}
​\frac{\varphi(s,t)}{s+ti}&=\frac{[u(x+s,y+t)-u(x,y)]-[u_x(x,y)s+u_y(x,y)t]}{s+ti}\\\\\
&=\frac{[u(x+s,y+t)-u(x,y+t)]+[u(x,y+t)-u(x,y)]-[u_x(x,y)s+u_y(x,y)t]}{s+ti}\\\\\
&=\frac{u_x(x+s_1,y+t)s+u_y(x,y+t_1)t-[u_x(x,y)s+u_y(x,y)t]}{s+ti}\\\\\
&=\frac{s}{s+ti}[u_x(x+s_1,y+t)-u_x(x,y)]+\frac{t}{s+ti}[u_y(x,y+t_1)-u_y(x,y)]
\end{split}\\]
Observe that \\(\left|\frac{s}{s+ti}\right|,\left|\frac{t}{s+ti}\right|\leq 1\\). Moreover, since \\(|s_1|<|s|\\) and \\(|t_1|<|t|\\), taking \\(s,t\to0\\) will force \\(s_1,t_1\to0\\). Hence, the last line above gives
​\\[\lim_{s+ti\to0}{\frac{\varphi(s,t)}{s+ti}}=0.\\]
Similarly, one can check that
\\[\psi(s,t)=[v(x+s,y+t)-v(x,y)]-[v_x(x,y)s+v_y(x,y)t]\\]
satisfies
​\\[\lim_{s+ti\to0}{\frac{\psi(s,t)}{s+ti}}=0.\\]
​Now, we can compute
\\[\begin{split}
\frac{g(z,s+ti)-g(z)}{s+ti}&=\frac{u(x+s,y+t)+iv(x+s,y+t)-u(x,y)-iv(x,y)}{s+ti}\\\\\
&=\frac{u(x+s,y+t)-u(x,y)}{s+ti}+i\frac{v(x+s,y+t)-v(x,y)}{s+ti}\\\\\
&=\frac{u_x(x,y)s+u_y(x,y)t+\varphi(s,t)}{s+ti}+i\frac{v_x(x,y)s+v_y(x,y)t+\psi(s,t)}{s+ti}\\\\\
&=\frac{u_x(x,y)s+u_y(x,y)t}{s+ti}+i\frac{v_x(x,y)s+v_y(x,y)t}{s+ti}+\frac{\varphi(s,t)+i\psi(s,t)}{s+ti}\\\\\
&=u_x(x,y)+iv_x(x,y)+\frac{\varphi(s,t)+i\psi(s,t)}{s+ti}.
\end{split}\\]
The last line is where we finally invoke the assumption that \\(u\\) and \\(v\\) satisfy the Cauchy-Riemann equations. Taking the limit \\(s+ti\to0\\) and using our above results on how \\(\varphi\\) and \\(\psi\\) will behave in these limits, we obtain
\\[g'(z)=(u_x\circ h)(z)-i(v_x\circ h)(z).\\]
Since the partial derivatives of \\(u\\) and \\(v\\) are continuous and \\(h\\) is continuous, we conclude that \\(g'\\) is continuous. That is, \\(g\\) is continuously differentiable on \\(G\\).

It turns out that complex differentiability in a neighborhood of every point of the domain (holomorphicity) is a strong condition that implies pretty much all the nice things that you would want. In fact, it implies that the function is infinitely complex differentiable and analytic. In the future, I will talk about these relationships, which form the core of complex analysis.