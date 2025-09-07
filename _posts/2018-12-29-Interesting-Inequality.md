---
layout: post
title: "Interesting Inequality"
date: 2018-12-29 10:00:00
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

This is from Volume 2 (AoPS). Problem 216. Show that for any two positive real numbers \\(a\\) and \\\(b\\),
\\[\frac{a+b}{2}-\sqrt{ab}\geq\sqrt{\frac{a^2+b^2}{2}}-\frac{a+b}{2}\\]
by showing that this inequality is equivalent to
​\\[\frac{(a+b)^2}{2}\geq\sqrt{2ab(a^2+b^2)}\\]
and then using the AM-GM Inequality.

This is a two part problem, so I will split the solution in two parts. I am posting this here because the algebraic manipulation for part 1 is cute, I used the trivial inequality instead of AM-GM for part 2, and overall, this is too insignificant to merit an entire PDF. I must confess, I solved part 2 before part 1.

**Part 1:** At first, this seems intractable because we need to somehow end up with the square root of a product. After about twenty seconds of "what even is this" staring, I realize that the same term is on both sides of the inequality. OK. Now I have:
\\[a+b-\sqrt{ab}\geq\sqrt{\frac{a^2+b^2}{2}}\\]
Things became a lot more apparent once I wrote:
\\[a+b\geq\sqrt{\frac{a^2+b^2}{2}}+\sqrt{ab}\\]
Now if I square the inequality and divide by 2, the LHS matches the LHS of our destination! Hence, it suffices to show that the resulting RHS is equivalent to the destination RHS. In particular, we have:
\\[(a+b)^2\geq\frac{a^2+b^2}{2}+2\sqrt{\frac{1}{2}ab(a^2+b^2)}+ab\\]
Dividing by two:
\\[\frac{(a+b)^2}{2}\geq\frac{a^2+b^2}{4}+\sqrt{\frac{1}{2}ab(a^2+b^2)}+\frac{ab}{2}\\]
Now we can work on the RHS:
\\[\frac{a^2+b^2}{4}+\sqrt{\frac{1}{2}ab(a^2+b^2)}+\frac{ab}{2}=\frac{a^2+b^2+2ab}{4}+\sqrt{\frac{1}{2}ab(a^2+b^2)}\\]
Which is:
\\[\frac{(a+b)^2}{4}+\sqrt{\frac{1}{2}ab(a^2+b^2)}\\]
At this point, I had didn't really have any ideas as to how to turn this into \\\(\sqrt{2ab(a^2+b^2)}\\). It wasn't until I took a look at the LHS of the inequality once again when I realized that I could subtract \\\(\frac{(a+b)^2}{4}\\) from both sides and then multiply by two to obtain the desired:
\\[\boxed{\frac{(a+b)^2}{2}\geq\sqrt{2ab(a^2+b^2)}}\\]

**Part 2:** When I'm solving a problem that is dependent on clever algebraic manipulations, I essentially think about terms that would result from possible operations in my head. I find this to be a great way to narrow down what operations need to be performed to make any progress. In this case, we have:
\\[\frac{(a+b)^2}{2}\geq\sqrt{2ab(a^2+b^2)}\\]
The \\(a^2+b^2\\) and the \\(2ab\\) in the radical were just too alarming to ignore. Especially considering that we obtain these very terms in the expansion of the LHS. In fact, I was so certain that these terms would be preserved that I went ahead and let \\(x=a^2+b^2\\) and \\(y=ab\\). Hence:
\\[\frac{x}{2}+y\geq\sqrt{2xy}\\]
Squaring:
\\[\frac{x^2}{4}+xy+y^2\geq2xy\\]
Standard manipulations turns this into:
\\[x^2-4xy+4y^2\geq0\\]
But this factors!
\\[(x-2y)^2\geq0\\]
Which is true by the Trivial Inequality. \\(\square\\)

I'm not sure what the AM-GM solutions was. My issue is that this solution just seems so overwhelmingly natural... those \\(a^2+b^2\\) and \\(ab\\) terms were just begging for substitution. Perhaps I just need a better grasp on nontrivial inequalities...

EDIT: Never mind, I just realized that the results follows from AM-GM on:
\\[\frac{x}{2}+y\geq\sqrt{2xy}\\]
The reason I did not observe this in my original solution is because I actually bothered to make my substitutions after completely expanding everything to eliminate the radical. This eliminated the radical symbol that is apparently so necessary for my brain to realize that AM-GM is a viable option. I am confident that if I had made my substitution earlier, I would have used AM-GM. Man, after such a long hiatus, I am rusty.
