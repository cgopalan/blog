---
layout: post
title: "Big-O notation"
date: 2012-10-02
---

Its a way to denote the worst-case running time of an algorithm based

System Message: WARNING/2 (/Users/cgopalan/my_blog/content/2012-10-02-big-o-notation.rst, line 10)
Line block ends without a blank line.
on input size.Note, Big-O does not automatically imply worst-case. We
just use it as a notation for worst-case running times.
| Say an algorithm's running time is T(n).
| Q: When is T(n) = O(f(n))? ("Big Oh f of n")
| A: If eventually, for all sufficiently large n, T(n) is bounded above
|  by a constant multiple of f(n).
|
|  Mathematically:
|  T(n) = O(f(n)) if an only if there exists constants C, n0 > 0
|  such that T(n) <= C * f(n) for all n >= n0.
|
|  Both n0 and C should be independent of n.
|
|  Note: If we have T(n) as a polynomial with the highest order term as
n**k,
|  then T(n) = O(n**k), i.e. lower order terms don't matter.
|
|