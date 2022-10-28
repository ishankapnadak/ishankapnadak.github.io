---
title: 'Complexity Classes and P v/s NP'
date: 2022-10-28
permalink: /posts/2022/10/complexity/
tags:
  - computer science
  - math
  - algorithms
katex: true
excerpt: 'On various complexity classes and their interplay'
---

Most algorithms one studies in an introductory algorithms class are polynomial-time algorithms that have a worst-case running time of $$\mathcal{O}(n^k)$$ for some constant $$k$$ on inputs of size $$n$$. A natural question is this: Are all problems solvable in polynomial time? The answer is an emphatic no. In fact, there are some problems which cannot be solved no matter how long we take (for example, the Halting Problem). There are also some 'intermediate' problems - problems that can be solved, just not in polynomial time. Problems with polynomial-time solutions are considered to be tractable. It is thus important to determine if a given problem lends itself to a polynomial time algorithm. A class of problems that plays a crucial role is the class of '$$NP$$-complete' problems. These are basically problems for which no polynomial time algorithm is known, nor is it proven that no such algorithm can exist. A deep open problem problem in computer science is whether $$P = NP$$. We formalize these classes and have a look at how they interact with each other.

## The Classes $$P$$ and $$NP$$