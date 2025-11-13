---
layout: post
title: "Zariski Topology"
date: 2022-6-6 12:00:00 -0400
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
math: true
---

Recently, I have been thinking and learning a lot about algebraic geometry. I decided to write about the Zariski topology in my final project for my introductory algebraic geometry class. You can find the paper <a href="/bay/myassets/docs/BlogDocs/ZariskiTopology.pdf" target="_blank">here</a>.

I mainly discuss some of the basic topological properties of the Zariski topology on affine space. These are all elementary properties of the Zariski topology, but it is difficult to find a source anywhere actually listing these properties with proof, so I found it to still be instructive to think about the proofs. One remarkable thing is that one can use the Zariski topology to prove the <a href="https://en.wikipedia.org/wiki/Cayley%E2%80%93Hamilton_theorem" target="_blank">Cayley-Hamilton theorem</a>, which is something I wrote about. I essentially filled in the details from <a href="https://www.aergus.net/blog/posts/using-zariski-topology-to-prove-the-cayley-hamilton-theorem.html" target="_blank">here</a>. The proof essentially shows that the collection of operators that have distinct eigenvalues is dense with respect to the Zariski topology. Since affine space is compact with that topology, the result really tells us that the collection of operators with distinct eigenvalues is precompact. This is a result reminiscent of the Arzelà-Ascoli theorem, which led me to wonder if affine space is sequentially compact under the Zariski topology. My hunch is that this is false.

I also briefly allude to the Zariski topology on the spectrum of a ring, but I don't really say much of substance about this. Over the summer, I plan on fleshing out this section and making precise the relationship between the topology on affine space and the topology on the spectrum of a ring. Based on what I've worked through in Atiyah-MacDonald, this relationship is not very easy to state.