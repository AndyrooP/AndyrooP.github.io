---
layout: post
title: "Another cute one"
date: 2019-8-12 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Here is a cute problem from Sweden. It is simply stated. Solve
\\[(\sqrt{2}-1)^x+(\sqrt{2}+1)^x=6.\\]
Before reading on, I *strongly* encourage you to give this a shot yourself. This is one of those problems that make you slap your forehead in disgust when you see the solution because it's so dumb simple.

Ok. Here's my solution.

We multiply through with, say, \\((\sqrt{2}+1)^x\\). This gives us
\\[1^x+(\sqrt{2}+1)^{2x}=6(\sqrt{2}+1)^x.\\]
But \\(1^x=x\forall x\in\mathbb{R}\\) so
\\[1+(\sqrt{2}+1)^{2x}=6(\sqrt{2}+1)^x.\\]
Aha! Now this is quadratic in \\((\sqrt{2}+1)^x\\). Letting \\(y=(\sqrt{2}+1)^x\\), we have
\\[y^2-6y+1=0,\\]
from which we find the roots to be
\\[y=3\pm2\sqrt{2}.\\] 
Hence,
\\[(1+\sqrt{2})^x=3\pm2\sqrt{2}\\]
and we have our two solutions
\\[\boxed{x=\log_{1+\sqrt{2}}{(3\pm2\sqrt{2})}=\pm2}\\]
​Haha...