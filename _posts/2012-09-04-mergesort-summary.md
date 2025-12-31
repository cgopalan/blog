---
layout: post
title: "Mergesort summary"
date: 2012-09-04
---

Mergesort advantage:

Running Time is **O(nlogn)** which is better than O(n**2)

Procedure:
Recursively sort each half. Merge at every step.
Running time of merge operation = k * n for an array of n elements

System Message: WARNING/2 (/Users/cgopalan/my_blog/content/2012-09-04-mergesort-summary.rst, line 26)
Line block ends without a blank line.
where k is the number of instructions to process on element.
| We can use the 'Recursion tree' method to calculate running time.
| Draw the sort out as a tree. The level number of the leaves is log n.
(logn + 1 to be exact if you count the root node)
| At each level j, there are 2**j subproblems.
| The subproblem size is n /(2**j) since its halved every level.
| Now work done at each level:
| Work to do recursive call + Work to do merge ~ Work to do merge.
| Work to do merge = k.n where n is problem size.
| Work to do merge at level for one subproblem j = k * (n/(2**j))
| Work to do merge at level for ALL 2**j subproblems
| = 2**j * k * (n/(2**j)) = k.n (independent of j!)
| Conceptually it is independent because the proliferation of
subproblems
| is canceled out by the decreasing subproblem size.
| Total work done in mergesort = work at each level * number of levels
| = k*n * (log n + 1)
| = k*n*logn + k*n
| ~ nlogn.