---
layout: post
title: "Strengthening a solution to a combinatorial problem"
date: 2019-7-22 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Suppose every point in \\(\mathbb{R}^2\\) is colored red, green, or blue. Let us prove that there exists a rectangle in this space whose vertices are all the same color.

The standard solution is to consider a \\(4\times82\\) grid. By Pigeonhole, there must exist at least two common colors in each column. Since there are \\(3^4=81\\) ways unique colorings of a column, once again by Pigeonhole, one of the columns must also be repeated in this grid. So there must be a rectangle whose vertices are the same color from these two columns.

However, we may strengthen the construction to a \\(4\times19\\) grid as follows. Observe that there are \\(\binom{4}{2}=6\\) ways to choose the two points in a column that are guaranteed to share a color and there are \\(3\\) ways to color those two points. This gives a maximum of \\(18\\) unique columns that do not necessarily share repeated colors in the same rows. Hence, by Pigeonhole, a \\(4\times19\\) grid *must* contain two columns with their minimum of two common colors in the same rows.

​Neat.