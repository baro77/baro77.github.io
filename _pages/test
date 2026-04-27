---
layout: page
title: test
permalink: /test/
---

To brush up surface codes I'm reading "*The Hitchhiker’s Guide to the Surface Code*" by Fang Zhang and Jianxin Chen ([https://doi.org/10.3390/e28020251][1])

On page 15 and 16 it deals with 3D MWPM taking into account not only qubit errors but also ancilla measurement errors.

In the last lines of page 16 and the first of page 17, dealing with short cycles between consecutive layers as difference of equally valid errors interpretations, it states:

> This also means that we do not care if such a cycle is the difference between the
actual error configuration and our correction. For example, suppose that $P_1$ and $P_2$ are two adjacent stabilizers, and the set of non-zero detectors we observe is {$∆_{P_1,1}$, $∆_{P_2,2}$}, meaning that the measurement results of both $P_1$ and $P_2$ have flipped once each, but $P_2$ flipped one round later than $P_1$. This can be interpreted in two ways:
• The qubit error that flips {$P_1$, $P_2$} occurred after round 1, but P2 was measured incorrectly in round 2, thus not properly reflecting the flip until round 3.
• The qubit error that flips {$P_1$, $P_2$} occurred after round 2, **but P1 was measured incorrectly in round 1**, thus seemingly flipping one round earlier.
We cannot distinguish between these two cases, but fortunately we do not need to.

My doubt is that, in second interpretation, P1 should have been incorrectly measured **in round 2, not round 1**.

Infact:

 1. Stabilizer $P$ measurement result at round $i$ is defined as $r_{P,i}$
 2. Stabilizer detector $∆_{P,i}$ is defined as $∆_{P,i}=r_{P,i} \oplus r_{P,i+1}$ and contained in layer between round $i$ and round $i+1$
 3. Ancilla measurement error at round $i$ flips detectors $∆_{P,i}$ and $∆_{P,i-1}$ (a part from boundaries where we have just one detector)
 4. A qubit error between round $i$ and round $i+1$ will flip two stabilizers $P_1$ and $P_2$,and so detectors $∆_{P_1,i}$ and $∆_{P_2,i}$

That said:

|round|1st interpretation|PAPER 2nd interpretation|MY 2nd interpretation|layer-spanning short cycle|
|-----|------------------|------------------------|---------------------|-----------|
|  3  |
|*layer*|| qubit error $\implies$ $∆_{P_1,2}$,$∆_{P_2,2}$ | qubit error $\implies$ $∆_{P_1,2}$,$∆_{P_2,2}$ | qubit error $\implies$ $∆_{P_1,2}$,$∆_{P_2,2}$ |
|  2  | $P_2$ measure error $\implies$ $∆_{P_2,2}$,$∆_{P_2,1}$ (in layers) ||**$P_1$ measure error $\implies$ $∆_{P_1,2}$,$∆_{P_1,1}$ (in layers)**|$P_1$,$P_2$ measure error $\implies$ $∆_{P_1,2}$,$∆_{P_1,1}$,$∆_{P_2,2}$,$∆_{P_2,1}$ (in layers)
|*layer*| qubit error $\implies$ $∆_{P_1,1}$,$∆_{P_2,1}$ |||qubit error $\implies$ $∆_{P_1,1}$,$∆_{P_2,1}$ |
|  1  ||**$P_1$ measure error $\implies$ $∆_{P_1,1}$ (in layer)**|

Please note that, as earlier recapped in point 2, detectors are contained into layers, so detectors flipped by a round measure have to be thought into layers just beneath and just over that round; so, e.g., lower layer in *1st interpretation* column will contain $∆_{P_2,1}$ two times, and both layers in *layer-spanning short cycle* column will have every detector twice: **it seems to me to be exactly the graphical representation of detectors "mutual cancellation" by means horizontal and vertical edges intersection**, given that the *layer-spanning short cycle* (with all detectors doubled) doesn't produce any visible error trace.

So I cannot understand how second column can differs from the first one by means of the last (while imho it works for third column); and even without relying on "graphical thinking", it seems to me that paper 2nd interpretation should result in three non-zero detectors, not only the two stated. 
