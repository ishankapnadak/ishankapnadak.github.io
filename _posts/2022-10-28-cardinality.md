---
title: 'Cardinality and Countability'
date: 2022-10-28
permalink: /posts/2022/10/cardinality/
tags:
  - math
  - set theory
katex: true
excerpt: 'On countable and uncountable sets and their cardinalities'
---

One often encounters infinite sets in everyday life. The set of natural numbers, the set of real numbers, and so on. Although these sets are infinite, it is natural to ask if one is ''bigger'' than the other. Are two infinite sets of the same size? In the case of finite sets, comparing two cardinalities is trivial. For example, the set $$\{A,B\}$$ is smaller than the set $$\{\alpha, \beta, \gamma\}$$ since the former has two elements whereas the latter has three. Easy so far. How do we compare the size of the set of natural numbers with, say, the set of integers? One may argue that the set of natural numbers is a proper subset of the set of integers and thus it ought to be a smaller set than the set of integers. However, another person may tell you that every natural number can be paired up with a unique integer. It makes sense then that the two sets are somehow of equal size. Although counterintuitive, we use this latter definition to formalize the notion of cardinalities for infinite sets. Under this framework then, the sets $$\mathbb{N}$$ and $$\mathbb{Z}$$ are equicardinal despite one being a proper subset of the other. We formalize these ideas below and analyze the cardinalities of some commonly encountered infinite sets.

## Comparing Cardinalities of two sets

We assume that the reader is familiar with common notions in set theory (in particular, the reader is hopefully familiar with the notion of sets, their unions and intersections, functions, their injectivity, surjectivity, and bijectivity). Georg Cantor came up with the idea of using functions between sets to compare their cardinalities. For example, if we are able to find a bijection between two sets, it must be the case that they have the same ''number'' of elements, that is, they are equicardinal. Similarly, if we are able to find an injection from one set into another, it must be the case that the latter set has ''at least as many elements'' as the former. These notions are formalized as follows.

1. Two sets $$A$$ and $$B$$ are **equicardinal** (denoted $$\lvert A \rvert = \lvert B \rvert$$) if there is a bijection from $$A$$ to $$B$$
2. $$B$$ has cardinality greater than or equal to $$A$$ (denoted $$\lvert A \rvert \geq \lvert B \rvert$$) if there is an injection from $$A$$ to $$B$$
3. $$B$$ has cardinality strictly greater than $$A$$ (denoted $$\lvert A \rvert > \lvert B \rvert$$) if there is an injection but no bijection from $$A$$ to $$B$$

With this in mind, we define countable sets as follows. A set $$E$$ is said to be **countably infinite** if $$E$$ and $$\mathbb{N}$$ are equicardinal. A set is said to be **countable** if it is either finite or countably infinite. Equivalently, a set $$E$$ is countable if $$\lvert E \rvert \leq \lvert \mathbb{N} \rvert$$. (Why?) 

## Countability of the Integers and the Rationals

Let us compare the sizes of $$\mathbb{N}$$ and $$\mathbb{Z}$$. We had claimed earlier that they are equicardinal. To prove this, all we have to do is establish a bijection between the two sets. We define $$f \colon \mathbb{Z} \to \mathbb{N}$$ as

$$
    f(n) = \begin{cases}
        2n & \text{if } n > 0, \text{ and} \\
        -2n + 1 & \text{if } n \leq 0.
    \end{cases}
$$

It is easy to verify that the above is a bijection. In particular, it sends positive integers to even numbers and negative integers to odd numbers. It follows then that $$\lvert\mathbb{N}\rvert = \lvert\mathbb{Z}\rvert$$ and thus $$\mathbb{Z}$$ is countable. 

We further claim that the set of rational numbers, $$\mathbb{Q}$$ is also countable. Proving this is slightly involved. We first restrict our attention to the rationals in the unit interval, that is, the set $$\mathbb{Q} \cap [0,1]$$. We define a step-by-step method to generate a bijection between $$\mathbb{N}$$ and $$\mathbb{Q} \cap [0,1]$$ by maintaining a list of rationals. Consider the rational number $$\frac{p}{q}$$ where $$q \neq 0$$. We start with $$q = 1$$ and increment $$q$$ by $$1$$ at every step. For each value of $$q$$, we iterate over all integers $$0 \leq p \leq q$$, we add $$\frac{p}{q}$$ to the list if it is not already present. 

We begin with an empty list and choose $$q = 1$$. For $$p = 0$$, the rational number we get is $$0$$, which is not included in the list, and hence is added to the list. Next, we take $$p = 1$$ to get the rational number $$1$$ and add this to the list too. Next, we update $$q$$ to $$2$$. Now, $$p = 0$$ gives us back $$0$$ and hence we move to $$p = 1$$. We get $$\frac{1}{2}$$ which is not present in the list, and hence add it to the list next. Proceeding this way, the rationals in the unit interval can be listed as

$$
  \left\{ 0, 1, \frac{1}{2}, \frac{1}{3}, \frac{2}{3}, \frac{1}{4}, \frac{3}{4}, \cdots \right\}.
$$

Furthermore, each rational in the unit interval appears exactly once in the above list and every number in the list is a rational in $$[0,1]$$. We can then clearly define a bijection from $$\mathbb{Q} \cap [0,1]$$ to $$\mathbb{N}$$ mapping $$\frac{p}{q}$$ to its index in the above list. This proves that $$\mathbb{Q} \cap [0,1]$$ are countable. 

We are not entirely done yet. To go from the rationals in the unit interval to the set of all rationals, we require one crucial theorem. Stated plainly, a countable union of countable sets is countable. A proof for this theorem is beyond the scope of this post, but can be viewed online. Equipped with this knowledge, we extend our result to the whole of $$\mathbb{Q}$$. To do so, we define $$ Q_n := \mathbb{Q} \cap [n, n+1]$$ for $$n \in \mathbb{Z}$$. We have already shown that $$Q_0$$ is countable. A similar argument shows that $$Q_n$$ is countable for each $$n \in \mathbb{Z}$$. Furthermore, since $$\mathbb{Z}$$ is countable, $$\bigcup_{n \in \mathbb{Z}} Q_n$$ is a countable union. But, the latter is just $$\mathbb{Q}$$, and thus we have represented $$\mathbb{Q}$$ as a countable union of countable sets. It follows that $$\mathbb{Q}$$ is countable. 

## Uncountability of Reals

Countable sets are sets $$E$$ with cardinality $$\lvert E \rvert \leq \lvert \mathbb{N} \rvert$$. Naturally, a set $$E$$ is said to be **uncountable** if $$\lvert E \rvert > \lvert \mathbb{N} \rvert$$. Stated more explicitly, a set $$E$$ is uncountable if there is an injection from $$E$$ to $$\mathbb{N}$$ but no bijection from $$E$$ to $$\mathbb{N}$$. One interesting example of an uncountable set is the set of infinite binary strings, a proof of which uses Cantor's famous 'diagonal argument'.

**Theorem.** The set of all infinite binary strings $$\{0, 1\}^{\infty}$$ is uncountable.

*Proof.* It is easy to produce an injection from $$\mathbb{N}$$ to $$\{0, 1\}^{\infty}$$ and we leave it as an exercise to the reader to do so. Assume to the contrary that there is also a bijection $$ f \colon \{0, 1\}^{\infty} \to \mathbb{N}$$. The set of infinite binary strings can then be listed as

$$ 
  \begin{pmatrix}
    a_{11} & a_{12} & a_{13} & \cdots \\
    a_{21} & a_{22} & a_{23} & \cdots \\
    a_{31} & a_{32} & a_{33} & \cdots \\
    \vdots & \vdots & \vdots & \ddots
  \end{pmatrix}
$$

where $$a_{ij}$$ represents the $$j^{\text{th}}$$ bit of the $$i^{\text{th}}$$ string. Now, consider the binary string formed by looking at all the diagonal elements above and complementing each bit. This gives us the string $$\overline{a} = \overline{a}_{11} \overline{a}_{22} \overline{a}_{33} \cdots $$ where $$\overline{a}_{ij}$$ denotes the complement of bit $$a_{ij}$$.