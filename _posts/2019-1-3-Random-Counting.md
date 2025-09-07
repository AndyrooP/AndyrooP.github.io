---
layout: post
title: "Random Counting"
date: 2019-1-3 10:00:00
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

**Problem (Canada 1979):** A walk consists of a sequence of steps of length \\(1\\) taken in directions north, south, east, or west. A walk is self-avoiding if it never passes through the same point twice. Let \\(f(n)\\) denote the number of \\(n\\)-step self-avoiding walks which begin at the origin. Show that \\(2^n<f(n)\leq4\cdot3^{n-1}\\).

**Solution (Bored Andrew Paul):** Initially, I thought about this algebraically. I wrote:
\\[(0,0)\rightarrow(x_1,y_1)\rightarrow...\rightarrow (x_n,y_n)\\]
Where consecutive \\(x_i\\) and \\(y_i\\) could be equal. Furthermore:
\\[x_i\neq x_{i+1}\Rightarrow |x_{i+1}-x_i|=1\\]
And a similar expression for \\(y\\).
​
This told me precisely nothing. All I had done was encoded the words of the problem into mathematical symbols. So I decided to quickly get the obvious out of the way:
\\[f(n)<4^n\\]
But \\(4\cdot3^{n-1}\\)? How on earth was I going to improve the bound to that? The lower bound of \\(2^n\\) seemed a lot more friendly, so I decided to approach that first.

The upper bound of \\(4^n\\) resulted from counting the number of all paths with \\(4\\) possible directions. Likewise, \\(2^n\\) counted the number of all paths when only two directions were allowed. Then it hit me: choosing a horizontal and a vertical direction guaranteed that all paths generated would be self-avoiding (think about it: the net movement would be diagonal and you could not cancel out your progress in either dimension).

But there were exactly \\(2^2=4\\) ways I could choose the pairings of the directions (one for each quadrant the path would venture into). I immediately thought that this meant that not only did we have \\(f(n)>2^n\\), but also \\(f(n)>4\cdot2^n=2^{n+2}\\). However, this is false because this path construction technique of choosing a horizontal and vertical direction results in identical paths being constructed for paths that went along the axes. For instance, the path \\((0,0)\rightarrow(1,0)\rightarrow(2,0)\\) can be constructed by choosing either north and east or south and east because the only direction that matters for the construction of this path is east. Since each axis is bordered by two quadrants, each path along the axes will be counted \\(8\\) times. Since there are only \\(4\\) axes, we are over-counting the axes paths by exactly \\(4\\). Hence, we have established the following stronger result for \\(n>2\\):
\\[f(n)\geq2^{n+2}-4>2^n\\]
I observed that equality held for \\(n\in\{0,1,2\}\\).

Now all I had left was to show that \\(f(n)\leq4\cdot3^{n-1}\\). Suddenly, it struck me that it could be possible that the \\(4\\) in the expression could represent the number of ways I could choose the first step. If I could show that I had a maximum of \\(3\\) ways to choose the subsequent steps, I would be done. This would establish the upper bound of \\(4\cdot3^{n-1}\\). 

To do this, I thought like an ant. If I were a little ant that was trying to generate self-avoiding paths, how would I go about doing so? I realized that after my first step, no matter what, I could not backtrack. This automatically discounted one of the directions from the set of possible directions I could go in to ensure that my path remained self-avoiding, leaving at most \\(3\\) directions left to choose from. The equality condition occurred when \\(n\in\{1,2\}\\).

Hence, I concluded, for \\(n\geq2\\):
\\[\boxed{2^n<2^{n+2}-4\leq f(n)\leq4\cdot3^{n-1}<4^n}\\]
The equality conditions are satisfied at \\(n=2\\). Fun stuff! Canadian problems always tickle my fancy.