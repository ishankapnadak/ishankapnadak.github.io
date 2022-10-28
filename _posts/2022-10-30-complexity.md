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

Most algorithms one studies in an introductory algorithms class are polynomial-time algorithms that have a worst-case running time of $$\mathcal{O}(n^k)$$ for some constant $$k$$ on inputs of size $$n$$. A natural question is this: Are all problems solvable in polynomial time? The answer is an emphatic no. In fact, there are some problems which cannot be solved no matter how long we take (for example, the Halting Problem). There are also some 'intermediate' problems - problems that can be solved, just not in polynomial time. Problems with polynomial-time solutions are considered to be tractable. It is thus important to determine if a given problem lends itself to a polynomial time algorithm. A class of problems that plays a crucial role is the class of 'NP-complete' problems. These are basically problems for which no polynomial time algorithm is known, nor is it proven that no such algorithm can exist. A deep open problem problem in computer science is whether P = NP. We formalize these classes and have a look at how they interact with each other.

## The Classes P and NP

We deal with decision problems. These are problems that have a yes/no answer. For example, given a natural number $$n$$, we may ask if $$n$$ is prime - a decision problem. An advantage of restricting ourselves to decision problems is that we can represent problems in the framework of a formal language. We let $$\Sigma$$ be an *alphabet* and $$\Sigma^*$$ be the set of all strings with letters from $$\Sigma$$. A *language* is then simply a subset of $$\Sigma^*$$. We mostly take $$\Sigma = \{0,1\}$$ so that $$\Sigma^*$$ is the set of all binary strings. With this in mind, each instance of a problem can be encoded as a string in $$\{0,1\}^*$$. The problem is characterized entirely by instances whose answer is yes. This can be encoded as a language $$L \subseteq \{0,1\}^*$$. For example, the decision problem PRIMES has the following language representation:

$$
  \text{PRIMES} = \left\{ x \in \{0,1\}^* \colon x \text{ represents a prime in binary} \right\}.
$$

An algorithm $$A$$ *accepts* (resp. *rejects*) a string $$x \in \{0,1\}^*$$ if the algorithm's output on input $$x$$ is a 1 (resp. 0). A language $$L$$ is *decided* by an algorithm $$A$$ if every string in $$L$$ is accepted by $$A$$ and every string not in $$L$$ is rejected by $$A$$. A language $$L$$ is *decided in polynomial time* by an algorithm $$A$$ if there exists a constant $$k > 0$$ such that for any $$n$$-length string $$x \in \{0,1\}^*$$, the algorithm correctly decides if $$x \in L$$ in time $$\mathcal{O}(n^k)$$.  Using this, the class P can be succinctly defined as:

$$
  \text{P} := \left\{ L \subseteq \{0,1\}^* \colon \text{there exists an algorithm } A \text{ that decides } L \text{ in polynomial time} \right\}.
$$