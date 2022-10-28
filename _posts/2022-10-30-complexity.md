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

Intuitively, problems in class $$P$$ are those that can be solved easily. For example, multiplication of two integers, division of two integers, etc. There are some algorithms for which we are able to *verify* a given solution in polynomial time. Problems of this type belong to class NP (Non-deterministic Polynomial-time Verifiable Problems). For example, it may be a hard problem to determine if a given graph has a Hamiltonian cycle (a simple cycle that contains each vertex) seems to be a hard problem. But if I give you a particular cycle and claim that it is a Hamiltonian cycle, it is easy to verify this in polynomial time. We define this class of problems formally.

A **verification algorithm** is a two-input algorithm $$A$$ where one argument is a regular binary input string $$x$$ and the other is a binary string $$y$$ called the *certificate*. A two-input algorithm $$A$$ *verifies* an input $$x$$ if there exists a certificate $$y$$ such that $$A(x,y) = 1$$. We now define the complexity class NP as follows. A language $$L$$ belongs to NP iff there exists a polynomial-time algorithm $$A$$ and a constant $$k$$ such that

$$
  L = \left\{x \in \{0,1\}^* \colon \text{there exists a certificate } y \text{ with } \lvert y \rvert = \mathcal{O}\left( \lvert x \rvert^k \right) \text{ such that } A(x,y) = 1 \right\}
$$

$$A$$ is said to *verify* $$L$ in polynomial time. Note that it is true by definition that $$P \subseteq NP$$, since every polynomial-time solvable problem is polynomial-time verifiable. A more interesting question to ask is where P $$=$$ NP. This remains an open problem in computer science, and is in fact one of the [Millenium Problems](https://www.google.com/search?q=millennium+problems&oq=millenium+pr&aqs=chrome.1.69i57j0i10i433i512j0i10i512l4j46i10i175i199i512j0i10i512l2j0i10i457i512.2468j0j7&sourceid=chrome&ie=UTF-8). Most computer scientists are of the opinion that the two are not the same class - that is, there is some polynoimal-time verifiable algorithm that is not polynomial-time solvable. A proof, though, ywt alludes us. A more compelling evidence of $$\text{P} \neq \text{NP}$$ is the existence of the NP-complete problems which we tackle next. 

## Polynomial-time Reduction and NP-Complete Problems

