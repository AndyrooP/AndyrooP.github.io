---
layout: post
title: "Centering Karel"
date: 2019-10-6 10:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---
Karel is a robot who exists on a two-dimensional grid. It is intended to provide a relevant scenario for first-time programming students to practice writing code and accomplishing tasks in such a way that they can visualize the results of the execution of their code. I am currently using Karel in my ECE 15 class.

Karel can,

- move forward one tile in the direction it is facing,
- rotate 90˚ either left or right,
- pick up items that are on the tile it is standing on and place it in its bag,
- take an item from its bag and place it on the tile it is on,
- detect if a wall is in front, to the left, or to the right of it,
- detect if an item is present on the tile which it is standing on,
- detect of its bag is empty,
- detect if it's facing a certain cardinal direction.


My professor posed the following challenge problem in my class.

Suppose Karel is at an arbitrary location in a row of an odd number of tiles, where each tile in the grid is empty and Karel has an infinite number of items in its bag. Find an algorithm that will bring Karel to the center of the row.

My solution is to first travel to one of the ends of the row (say, left). Place an item, travel two tiles, place an item, and continue placing an item every two tiles. Since the number of tiles in the row is odd, you will complete this process by placing an item on the opposite end. Then, pick up this item, travel back to the other end, and move forward one tile (the first empty tile). Place the item there. Travel back to right end and come back towards the right until you meet the next item square. Pick up this item and bring it to the next side in the same process of traveling back to the left end and then moving right until you encounter an empty square. 

It is important to note that *before* picking up the items, we must check to see that the tile just beyond it is not occupied by an item. If it is, we have fully transferred half of the items in the row to the other side of the row, and we can terminate the process. In that case, the last square on which we dropped an item is the center square! I may implement this in C later.