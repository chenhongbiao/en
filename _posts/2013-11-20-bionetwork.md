---
layout: post 
category : bioinformatics
matheq: yes
title: Hardship of bio-network analysis
comments: yes
share: no
tags : [math]
---
Any behaviour in any organism today is no longer simply an isolated process as decades before.
Proteins are interacted, genes coexpressed, signal conduction network, and metabolism conduction network and also there are high level network base on these fundamental networks, such as disease network and drug network, all of them are interacted with each other, cross-talk, repress or promote and so on.
OK, does it sound like a horrible nightmare? That you were precariously walking in an exhibition hall full of glassware, intoxicated, could not help yourself to touch the glassware, then it began to shake, which was worse, when you in your haste to rescue it, you broke a pile of glasswares behind you.
However, this bio-network thing has not reach its "chaos" climax yet.

#### Data

When talk about data, there is no way to avoid noise.
Sometimes, some researchers integrate one category of data, PPIs, as an example, integrate [DIP][DIP], [MINT][MINT], [IntAct][IntAct], it was good at the beginning, but seldom of them update their database timely thereafter, even if they keep abreast with [DIP][DIP], [MINT][MINT] and [IntAct][IntAct], we are not feeling safe to use the newly unchecked data.
Instead, we would rather to use a rigorous approach, sounds like we are the people suffer from obsessive-compulsive disorder.

#### Statistics

Bio-network data is huge, miscellaneous collection of nodes and edges between them.
For example, protein-protein interaction network curated in DIP database shows:

> Number of proteins	26268

> Number of interactions	76773

To visualize this network and adjust it smoothly, we need a PC with large RAM (> 8GB), softwares such as [R][R] or [Cytoscape][Cytoscape] or [Gephi][Gephi].
We will find out the network is so complicated, nodes are highly connected, to analyse it will be far beyond the reach of human brain.

We want to know whether the proteins in one module or motif in PPI network are coexpressed, we need to do some mathematical statistics.
The commonly used statistics and probability theories to analyse the network includes \\(\\chi\^2\\) test, hyper geometric test, student's t test.

To be simple and straightforward, the principle of these tests are just like an kind of spot check conducted by a boss .
Suppose, employees in an microchip factory produced a new batch of microchips, let's say 1,000,000 chips, denoted by \\(\\mathbb{X}\\).
Here's another concept, inferior rate \\(r\\), represents the proportion of inferior in \\(\\mathbb{X}\\).
Boss came and said, "hey, how about the quality?" 
Certain employee (Tom) gave an response, "inferior rate \\(p=0.05\\)", which means the possibility of every microchip being inferior is 0.05.
Anyway, response proposed by untrustworthy employees sounds suspiciously like a lie, which makes the boss conduct a spot check.
He randomly picked out 10,000 microchips (denoted by \\(\\mathbb{S}\\)), manually checked the quality of every microchip, at the end, he found out 32 inferior microchips.
The boss thought that if few people are more untrustworthy than Tom, then, Tom is untrustworthy.
So the boss calculated the probability of the sample being even more bizarre than this one as following,

$$ p\\\_value = \\sum\\limits\_{i=0}^{31} C\_{10,000}^{i} p^{31} (1-p)^{10,000-31} = 4.851154e^{-173}. $$

obviously, \\(p\\\_value\\) is so small that approximately equals 0.
According to this result, the boss presumably considered Tom didn't tell him the truth.

Everything is uncertain, even when we have a very small \\(p\\\_value\\), what we could merely proclaim is the hypothesis is presumably false.

[DIP]: http://dip.doe-mbi.ucla.edu/dip/ 
[R]: http://cran.r-project.org/ 
[Cytoscape]: http://www.cytoscape.org/ 
[Gephi]: http://www.gephi.org/ 
[IntAct]: http://www.ebi.ac.uk/intact/ 
[MINT]: http://mint.bio.uniroma2.it/mint/ 





