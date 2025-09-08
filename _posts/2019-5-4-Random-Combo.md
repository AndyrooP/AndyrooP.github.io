---
layout: post
title: "Random Combo"
date: 2019-5-4 10:00:00
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Feeling bad, need a quick post, here it is.

**Problem (HMMT):** Eight knights are placed on a chessboard. What is the probability that every square on the chessboard is attacked?

**Solution (Me):** Each knight can attack a maximum of eight squares. So all eight knights must all attack the maximum of eight squares each for the entire board of 64 squares to be attacked.

But for a corner square to be attacked, say h8, a knight must be on g6 or f7. But such a knight would attack less than eight squares, contradiction. The answer is 0.

**Problem (HMMT):** A true-false test has 10 questions. Suppose that if you answer any five questions "true" and the remaining five questions "false," then your score is guaranteed to be at least four. How many answer keys are there for which this is true?

**Solution (Me):** Suppose the answer key has 5 true and 5 false answers. Then, it is possible to attain a 0. WLOG (due to symmetry), let us increase the number of true answers to 6. Now, the worst we can do is a 1, as we place 4 T's where there should be F's, and we have a remaining T that is forced to be correct. Extrapolating this reasoning, we guarantee at least a 4 with 9 true and 1 false and at least a 5 with 10 true and none false. These two cases that work are counted by \\(\binom{10}{9}+\binom{10}{10}=11\\). Multiplying by two to account for symmetry, the answer is 22.

Combo is pretty hit or miss and I hit the next one pretty quickly.

**Problem:** Is there a 2000-element subset of the set \\(\{1,2,3,...,3000\}\\) such that no element in the subset is exactly double another element of the subset?

**Solution (Me):** Suppose the set is \\(A\\). Choose all the odds (obviously). This gives us 1500 elements. The remaining elements of \\(A\\) must be multiples of powers of \\(4\\). If we allow a multiples of powers of \\(2\\) that are not powers of \\(4\\), doubles will exist. The computation shows that we end up with \\(1999\\) terms, just short of the required \\(2000\\).

​I have a chess tournament tomorrow. Hopefully that's fun.