---
layout: post
title: "Stumbling Around"
date: 2019-2-8 10:00:00
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Last Saturday, on my way to a Mu Alpha Theta competition, I had an interesting thought.

I was thinking about how people could lie about their IQs by rounding them. Obviously, this is only really effective if your IQ increases upon rounding. For instance, it doesn't do any good to round an IQ of 132 to the nearest 10 because the result is actually less than 132.

Then, I realized that you could round to different numbers. For instance, with an IQ of 133, instead of rounding to the nearest 10, one could round to the nearest 5 to obtain 135. Sillily, I wondered what would happen if someone tried to further obscure their true IQ by rounding already rounded values. For instance, rounding 132 to the nearest 1 yielded, 132. Then, rounding that to the nearest 2 again yielded 132. Rounding to the nearest 3, we again have 132. Rounding to the nearest 4, we have 132. But when we round to the nearest 5, we drop down to 130. Now, we take 130 and round it to the nearest 6. This brings us back up to 132. Next, we are up to 133.

I quickly realized that this sequence was fascinating. It had a simple recursive definition: \\(a_n\\) was obtained by rounding \\(a_{n-1}\\) to the nearest \\(n\\).

I wrote a program to generate these sequences and what I found was quite shocking. Every single sequence seemed to converge to an arithmetic sequence after a certain number of terms. Let \\(a_k\\) be the particular term when the sequence enters an arithmetic sequence.

Results from my program seemed to imply that \\(a_k=\frac{k^2}{2}\\) for even \\(k\\) (this was actually an observation from William He). We did not explicitly find \\(a_k\\) for odd \\(k\\) initially.

It wasn't until I took the marker to the whiteboard when more progress was made. Observe that \\(a_n=np\\) for \\(p\in\mathbb{Z}\\). Hence, consecutive terms were given by \\(np\\) and \\((n+1)q\\) for \\(p,q\in\mathbb{Z}\\). For all \\(a_n\\), there exists a set of possible \\(q\\), which I will call \\(Q\\).

I was able to prove that *if* \\(p=\max{Q}\\), then \\(q=p\\). When \\(q=p\\), the sequence (obviously) becomes arithmetic. Furthermore, if this occurred, I was able to show that \\(a_k=\frac{k^2}{2}\\) for even \\(k\\) and that \\(a_k=\frac{k(k+1)}{2}\\) for odd \\(k\\). Running my program a couple of times, it seemed that for odd \\(k\\), the equation \\(a_k=\frac{k(k+1)}{2}\\) was actually true!

The problem is that I have not proven that \\(p\\) ever actually equals \\(\max{Q}\\). This is the final missing piece. I am confident, however, that I am correct, especially since my program is confirming my explicit formulas for \\(a_k\\).

The graphs of the sequence are even more beautiful. I graphed the sequence for starting terms of 500, 1000, and 2000, focusing on the behavior of the sequence before it converged to an arithmetic sequence.

<div style="text-align: center;">
<img src="/myassets/images/2019-2-8-Stumbling-Around-images/dia1.png" alt="Sequence graph for a_0=500" width="700px">
</div>

<div style="text-align: center;">
<img src="/myassets/images/2019-2-8-Stumbling-Around-images/dia2.png" alt="Sequence graph for a_0=1000" width="700px">
</div>

<div style="text-align: center;">
<img src="/myassets/images/2019-2-8-Stumbling-Around-images/dia3.png" alt="Sequence graph for a_0=2000" width="700px">
</div>

The number of bounces clearly increases as the first term increases. Also, the bounces appear to approach a parabolic shape as the first term is increased. These may be new avenues of investigation after I can prove that the sequence always converges to an arithmetic sequence.

​But for now, I'll keep looking for that missing piece.