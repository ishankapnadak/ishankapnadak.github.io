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

Most algorithms one studies in an introductory algorithms class are polynomial-time algorithms that have a worst-case running time of $$\mathcal{O}(n^k)$$ for some constant $$k$$ on inputs of size $$n$$. A natural question is this: Are all problems solvable in polynomial time? The answer is an emphatic no. In fact, there are some problems which cannot be solved no matter how long we take (for example, the Halting Problem). There are also some 'intermediate' problems - problems that can be solved, just not in polynomial time. Problems with polynomial-time solutions are considered to be tractable. It is thus important to determine if a given problem lends itself to a polynomial time algorithm. A class of problems that plays a crucial role is the class of '$$\text{NP}$$-complete' problems. These are basically problems for which no polynomial time algorithm is known, nor is it proven that no such algorithm can exist. A deep open problem problem in computer science is whether $$\text{P} = \text{NP}$$. We formalize these classes and have a look at how they interact with each other.

## The Classes P and NP

We deal with decision problems. These are problems that have a yes/no answer. For example, given a natural number $$n$$, we may ask if $$n$$ is prime - a decision problem. An advantage of restricting ourselves to decision problems is that we can represent problems in the framework of a formal language. We let $$\Sigma$$ be an *alphabet* and $$\Sigma^*$$ be the set of all strings with letters from $$\Sigma$$. A *language* is then simply a subset of $$\Sigma^*$$. We mostly take $$\Sigma = \{0,1\}$$ so that $$\Sigma^*$$ is the set of all binary strings. With this in mind, each instance of a problem can be encoded as a string in $$\{0,1\}^*$$. The problem is characterized entirely by instances whose answer is yes. This can be encoded as a language $$L \subseteq \{0,1\}^*$$. For example, the decision problem PRIMES has the following language representation:

$$
  \text{PRIMES} = \left\{ x \in \{0,1\}^* \colon x \text{ represents a prime in binary} \right\}.
$$

An algorithm $$A$$ *accepts* (resp. *rejects*) a string $$x \in \{0,1\}^*$$ if the algorithm's output on input $$x$$ is a 1 (resp. 0). A language $$L$$ is *decided* by an algorithm $$A$$ if every string in $$L$$ is accepted by $$A$$ and every string not in $$L$$ is rejected by $$A$$. A language $$L$$ is *decided in polynomial time* by an algorithm $$A$$ if there exists a constant $$k > 0$$ such that for any $$n$$-length string $$x \in \{0,1\}^*$$, the algorithm correctly decides if $$x \in L$$ in time $$\mathcal{O}(n^k)$$.  Using this, the class $$\text{P}$$ can be succinctly defined as:

$$
  \text{P} := \left\{ L \subseteq \{0,1\}^* \colon \text{there exists an algorithm } A \text{ that decides } L \text{ in polynomial time} \right\}.
$$

Intuitively, problems in class $$\text{P}$$ are those that can be solved easily. For example, multiplication of two integers, division of two integers, etc. There are some algorithms for which we are able to *verify* a given solution in polynomial time. Problems of this type belong to class $$\text{NP}$$ (Non-deterministic Polynomial-time Verifiable Problems). For example, it may be a hard problem to determine if a given graph has a Hamiltonian cycle (a simple cycle that contains each vertex). But if I give you a particular cycle and claim that it is a Hamiltonian cycle, it is easy to verify this in polynomial time. We define this class of problems formally.

A **verification algorithm** is a two-input algorithm $$A$$ where one argument is a regular binary input string $$x$$ and the other is a binary string $$y$$ called the *certificate*. A two-input algorithm $$A$$ *verifies* an input $$x$$ if there exists a certificate $$y$$ such that $$A(x,y) = 1$$. We now define the complexity class $$\text{NP}$$ as follows. A language $$L$$ belongs to $$\text{NP}$$ iff there exists a polynomial-time algorithm $$A$$ and a constant $$k$$ such that

$$
  L = \left\{x \in \{0,1\}^* \colon \text{there exists a certificate } y \text{ with } \lvert y \rvert = \mathcal{O}\left( \lvert x \rvert^k \right) \text{ such that } A(x,y) = 1 \right\}
$$

$$A$$ is said to *verify* $$L$$ in polynomial time. Note that it is true by definition that $$P \subseteq NP$$, since every polynomial-time solvable problem is polynomial-time verifiable. A more interesting question to ask is where $$\text{P} = \text{NP}$$. This remains an open problem in computer science, and is in fact one of the [Millenium Problems](https://www.google.com/search?q=millennium+problems&oq=millenium+pr&aqs=chrome.1.69i57j0i10i433i512j0i10i512l4j46i10i175i199i512j0i10i512l2j0i10i457i512.2468j0j7&sourceid=chrome&ie=UTF-8). Most computer scientists are of the opinion that the two are not the same class - that is, there is some polynomial-time verifiable algorithm that is not polynomial-time solvable. A proof, though, yet alludes us. A more compelling evidence of $$\text{P} \neq \text{NP}$$ is the existence of the $$\text{NP}$$-complete problems which we tackle next. 

## Polynomial-time Reduction and NP-Complete Problems

Let $$L_1, L_2$$ be two decision problems. A function $$f \colon \{0,1\}^* \to \{0,1\}^*$$ is called a *polynomial-time* reduction from $$L_1$$ to $$L_2$$ if 
1. There exists $$c$$ such that $$f(x)$$ is computable in time $$\mathcal{O}(\lvert x \rvert^c)$$, and
2. $$x \in L_1 \iff f(x) \in L_2$$. 

If such an $$f$$ exists we write $$L_1 \leq_p L_2$$. Intuitively, this means that any instance of $$L_1$$ can be 'rephrased' to an instance of $$L_2$$ in polynomial time. Moreover, providing an answer to $$f(x) \in L_2$$ instantly provides us an answer to $$x \in L_1$$. If we are able to find a polynomial-time algorithm $$L_2$$, this reduction lends itself to give us a polynomial time algorithm for $$L_1$$ as well. This is formalized as follows.

**Lemma.** If $$L_1, L_2 \subseteq \{0,1\}^*$$ are languages such that $$L_1 \leq_p L_2$$, then $$L_2 \in \text{P} \implies L_1 \in \text{P}$$.

With this, we define $$\text{NP}$$-complete problems as follows. A language $$L \subseteq \{0,1\}^*$$ is $$\text{NP}$$-complete if
1. $$L \in \text{NP}$$, and
2. $$L^{\prime} \leq_p L$$ for every $$L^{\prime} \in \text{NP}$$. 

If a language $$L \subseteq \{0,1\}^*$$ satisfies only condition 1 but not necessarily 2, we say that $$L$$ is $$\text{NP}$$-hard. We let $$\text{NPC}$$ be the class of all $$\text{NP}$$-complete problems. The question $\text{P} = \text{NP}$$ is closely related to solving $$\text{NP}$$-complete problems through the following theorem (the proof of which is left as an exercise). 

**Theorem.** If an $$\text{NP}$$-complete problem is polynomial-time solvable, then $\text{P} = \text{NP}$$. Equivalently, if any problem in $$\text{NP}$$ is not polynomial-time solvable, then no $$\text{NP}$$-complete problem is polynomial-time solvable. 

This theorem reinforces the idea that $$\text{NP}$$-complete problems are the 'hardest' $$\text{NP}$$ problems. As a class of problems, we can clearly see that $$\text{NP}$$-complete hold a special space - they are the hardest problems in $$\text{NP}$$. As such any polynomial time solution to an $$\text{NP}$$-complete problem warrants that $$ \text{P} = \text{NP}$$. A lot of crucial problems can be reduced to $$\text{NP}$$-complete problems via the following crucial theorem.

**Theorem.** If $$L^{\prime} \leq_p L$$ and $$L^{\prime}$$ is $$\text{NP}$$-complete, then $$L$$ is $$\text{NP}$$-hard. Additionally, if $$L \in \text{NP}$$, then $$L$$ is $$\text{NP}$$-complete. 

A proof is left as an exercise. There is a lot of literature regarding $$\text{NP}$$-complete problems and reductions from one problem to another. Here, we simply list an important class of $$\text{NP}$$-complete problems without proof. 

1. **CIRCUIT-SAT.** To determine whether a given Boolean circuit is satisfiable is $$\text{NP}$$-complete.
2. **3CNF-SAT.** A Boolean formula $$\Phi$$ of the form $$C_1 \wedge C_2 \wedge \cdots \wedge C_m$$ where each clause $$C_i$$ has the form $$(l_1^i \vee l_2^i \vee l_3^i)$$ is called a 3CNF formula. To determine whether a given 3CNF formula is satisfiable is an $$\text{NP}$$-complete problem.
3. **CLIQUE.** Given a graph $$G = (V,E)$$, a subset $$V_0 \subseteq V$$ is called a *clique* if $$\forall u,v \in V_0, u \neq v$$, we have $$(u,v) \in E$$. Determining whether a given graph $$G$$ has a clique of size $$k$$ is an $$\text{NP}$$-complete problem.
4. **IND.** Given a graph $$G = (V,E)$$, a subset $$V_0 \subseteq V$$ is called an *independent set* if $$\forall u,v \in V_0, u \neq v$$, we have $$(u,v) \notin E$$. Determining whether a given graph $$G$$ has an independent set of size $$k$$ is an $$\text{NP}$$-complete problem.
5. **GRAPH-COLORING.** A graph $$G = (V,E)$$ is $$k$$-*colorable* if there exists a function $$f \colon V \to \{1, \ldots, k\}$$ such that $$(u,v) \in E \implies f(u) \neq f(v)$$. Determing whether a given graph is $$k$$-colorable is an $$\text{NP}$$-complete problem for $$k > 2$$. Determining whether a graph is $$2$$-colorable is in $$\text{P}$$. 
6. **HAM-CYCLE.** Given an undirected graph $$G = (V,E)$$, a *Hamiltonian cycle* is a simple cycle where each vertex occurs exactly once. Determining whether a given graph $$G$$ has a Hamiltonian cycle is an $$\text{NP}$$-complete problem.
7. **TSP.** Given a complete directed graph $$G = (V,V \times V)$$ with non-negative integer weights $$c \colon V \times V \to \mathbb{N}$$, does there exist a Hamiltonian cycle (called a tour) with weight atmost $$k$$? The above problem is called the *Travelling Salesman Problem* and is $$\text{NP}$$-complete.
8. **SUBSET-SUM.** Given a finite set of positive integers $$S$$ and an integer $$t > 0$$, does there exist a subset $$S^{\prime} \subseteq S$$ such that $$\sum_{i \in S^{\prime}} i = t$$? This problem is called the *Subset-Sum Problem* and is $$\text{NP}$$-complete.

One thing that stands out is that all $$\text{NP}$$-complete problems (and in particular, the eight above) have, in some sense, equivalent complexity. If one is able to solve any one of these problems tractably (namely, in polynomial-time), the same holds true for all these problems, and in fact, for all $$\text{NP}$$ problems.

### References

1. [Lectures by Prof. Paritosh Pandya, IITB](https://www.cse.iitb.ac.in/~pandya58/cs218m/algo.html)
2. [*Introduction to Algorithms*, CLRS](https://en.wikipedia.org/wiki/Introduction_to_Algorithms)
