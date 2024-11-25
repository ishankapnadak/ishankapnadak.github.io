---
title: 'Cardinality and Countability'
date: 2022-10-28
permalink: /posts/2022/10/cardinality/
tags:
  - math
  - set theory
katex: true
excerpt: ''
---

One often encounters infinite sets in everyday life. The set of natural numbers, the set of real numbers, and so on. Although these sets are infinite, it is natural to ask if one is ''bigger'' than the other. Are two infinite sets of the same size? In the case of finite sets, comparing two cardinalities is trivial. For example, the set $$\{A,B\}$$ is smaller than the set $$\{\alpha, \beta, \gamma\}$$ since the former has two elements whereas the latter has three. Easy so far. How do we compare the size of the set of natural numbers with, say, the set of integers? One may argue that the set of natural numbers is a proper subset of the set of integers and thus it ought to be a smaller set than the set of integers. However, another person may tell you that every natural number can be paired up with a unique integer. It makes sense then that the two sets are somehow of equal size. Although counterintuitive, we use this latter definition to formalize the notion of cardinalities for infinite sets. Under this framework then, the sets $$\mathbb{N}$$ and $$\mathbb{Z}$$ are equicardinal despite one being a proper subset of the other. We formalize these ideas below and analyze the cardinalities of some commonly encountered infinite sets.

## Comparing Cardinalities of two sets

We assume that the reader is familiar with common notions in set theory (in particular, the reader is hopefully familiar with the notion of sets, their unions and intersections, functions, their injectivity, surjectivity, and bijectivity). Georg Cantor came up with the idea of using functions between sets to compare their cardinalities. For example, if we are able to find a bijection between two sets, it must be the case that they have the same ''number'' of elements, that is, they are equicardinal. Similarly, if we are able to find an injection from one set into another, it must be the case that the latter set has ''at least as many elements'' as the former. These notions are formalized as follows.

1. Two sets $$A$$ and $$B$$ are **equicardinal** (denoted $$\lvert A \rvert = \lvert B \rvert$$) if there is a bijection from $$A$$ to $$B$$
2. $$B$$ has cardinality greater than or equal to $$A$$ (denoted $$\lvert B \rvert \geq \lvert A \rvert$$) if there is an injection from $$A$$ to $$B$$
3. $$B$$ has cardinality strictly greater than $$A$$ (denoted $$\lvert B \rvert > \lvert A \rvert$$) if there is an injection but no bijection from $$A$$ to $$B$$

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

## Uncountability of the Reals and the Irrationals

Countable sets are sets $$E$$ with cardinality $$\lvert E \rvert \leq \lvert \mathbb{N} \rvert$$. Naturally, a set $$E$$ is said to be **uncountable** if $$\lvert E \rvert > \lvert \mathbb{N} \rvert$$. Stated more explicitly, a set $$E$$ is uncountable if there is an injection from $$\mathbb{N}$$ to $$E$$ but no bijection from $$\mathbb{N}$$ to $$E$$. One interesting example of an uncountable set is the set of infinite binary strings, a proof of which uses Cantor's famous 'diagonal argument'.

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

where $$a_{ij}$$ represents the $$j^{\text{th}}$$ bit of the $$i^{\text{th}}$$ string. Now, consider the binary string formed by looking at all the diagonal elements above and complementing each bit. This gives us the string $$\overline{a} = \overline{a}_{11} \overline{a}_{22} \overline{a}_{33} \cdots $$ where $$\overline{a}_{ij}$$ denotes the complement of bit $$a_{ij}$$. Now, let $$f(\overline{a}) = k$$ which means that the string $$\overline{a}$$ occurs in the $$k^{\text{th}}$$ position in the above table. Note that the $$k^{\text{th}}$$ bit of $$\overline{a}$$ is $$\overline{a}_{kk}$$ by definition, whereas the $$k^{\text{th}}$$ bit of the $$k^{\text{th}}$$ string in the table above is $$a_{kk}$$ which is a contradiction. It then follows that no such bijection exists and $$\{0,1\}^{\infty}$$ is thus uncountable. 

Next, we prove that the unit interval $$[0,1]$$ is uncountable. To do so, we simply prove that it is equicardinal with the set of infinite binary strings, from which it follows that it is uncountable. We come up with a bijection from $$\{0,1\}^{\infty}$$ to $$[0,1]$$. One natural way to do is to consider the infinite binary string to be the binary expansion of a number in $$[0,1]$$ (that is, the string represents the binary expansion post the binary point). For any infinite binary string $$ x = (x_1, x_2, \ldots) \in \{0,1\}^{\infty}$$, we define 

$$
  g(x) = \sum_{k=1}^{\infty} x_k \cdot \frac{1}{2^k}.
$$

Is $$g(\cdot)$$ as defined above a bijection? On the face of it, it appears so. But it isn't. The function $$g$$ maps $$\{0,1\}^{\infty}$$ ''almost bijectively'' to $$[0,1]$$. The only points of issue are the 'dyadic rationals', that is, rationals of the form $$\frac{a}{2^b}$$. These numbers have two pre-images. For example, $$g(1000 \cdots) = g(0111 \cdots) = \frac{1}{2}$$. This doesn't post a big problem though. Note that the dyadic rationals are a subset of the rationals and are thus countable. We can order them very naturally as per the following list

$$
  \mathcal{D} = \left\{ d_1 = \frac{1}{2}, d_2 = \frac{1}{4}, d_3 = \frac{3}{4}, d_4 = \frac{1}{8}, d_5 = \frac{3}{8}, d_6 = \frac{5}{8}, d_7 = \frac{7}{8}, \cdots \right\}.
$$

We use this to explicitly construct a bijection as follows. Define $$ f \colon \{0,1\}^{\infty} \to [0,1]$$ as

$$
  f(x) = \begin{cases}
    g(x) & \text{if } g(x) \notin \mathcal{D}, \\
    d_{2n-1} & \text{if } g(x) = d_n \text{ for some } n \in \mathbb{N} \text{ and } x \text{ terminates in } 1, \text{ and} \\
    d_{2n} & \text{if } g(x) = d_n \text{ for some } n \in \mathbb{N} \text{ and } x \text{ terminates in } 0.
  \end{cases}
$$

This is a bijection, proving that $$[0,1]$$. To go from $$[0,1]$$ to $$\mathbb{R}$$ is fairly straightforward, by considering a bijection from $$(0,1)$$ to $$\mathbb{R}$$. One possible bijection is $$ x \mapsto \tan\left( \pi x - \frac{pi}{2} \right)$$. The set of irrationals is simply $$\mathbb{R} \setminus \mathbb{Q}$$. Since $$\mathbb{R}$$ is uncountable and $$\mathbb{Q}$$ is countable, it follows that the irrationals are uncountable (Hint: prove by contradiction).

## Transfinite Cardinals and the Continuum Hypothesis

Set theory often uses special symbols to denote infinities. More specifically, we use ''transfinite cardinals'' - a sequence of numbers that denote the cardinality of infinite, well-orderable sets. We omit the well-orderable part for now. The cardinality of the natural numbers is denoted as $$\aleph_0$$ and is, in some sense, the ''smallest'' infinity. More precisely, any infinite set is either in bijection with the natural numbers or is uncountable (that is, there is no infinite set that is 'strictly smaller' than the naturals). The next larger cardinality of an infinite well-orderable set is denoted $$\aleph_1$$, followed by $$\aleph_2$$ and so on. 

Where do the reals fit in this heirarchy exactly? Well, it is important to note that the set of real numbers is in bijection with the power set of the natural numbers (Hint: provide a bijection between the power set of $$\mathbb{N}$$ and the set $$\{0,1\}^{\infty}$$). The cardinality of $$\mathbb{R}$$ is therefore $$2^{\aleph_0}$$. Since $$\mathbb{R}$$ is uncountable, we have already shown that $$2^{\aleph_0} > \aleph_0$$. But where exactly does it fit in the heirarchy of transfinite cardinals? Since $$\mathbb{R}$$ is an infinite well-orderable set, its cardinality, $$2^{\aleph_0}$$, must be some transfinite cardinal. But which one? Is it $$\aleph_1$$? Or $$\aleph_2$$? Or perhaps $$\aleph_{42}$$? Well, the fact is that we don't really know. We know that $$\aleph_1$$ is the second largest transfinite cardinal (or the second largest ''infinity'', if you would), but we don't really know what it counts. Is there some uncountable subset of $$\mathbb{R}$$ that has cardinality $$\aleph_1$$? We don't know. This leads us to the continuum hypothesis. 

Once we have established the existence of two infinite sets with different sizes (namely, $$\mathbb{N}$$ and $$\mathbb{R}$$), it is natural to ask if there is an infinite set of *intermediate size*. Cantor dealt with this problem for quite a while, trying to come up with subsets of $$\mathbb{R}$$ that could not be put in bijection with either the reals or the naturals. The continuum hypothesis (CH) claims that there is no such set, in which case the reals are the second-largest infinite set. That is, $$\aleph_1 = 2^{\aleph_0}$$. The question remains - is the continuum hypothesis true? The (possibly unsatisfactory) answer is that the hypothesis itself is undecidable under the standard axioms of set theory (ZFC). That is, we cannot construct (using only axioms from ZFC) a set with cardinality strictly between $$\mathbb{N}$$ and $$\mathbb{R}$$, and neither can we prove its non-existence. More specifically, it is possible to add either CH or its negation to ZFC and still remain consistent. Kurt Gödel constructed a model of ZFC in which CH is true, whereas Paul Cohen constructed a model of ZFC where CH is false. What this really means is that ZFC is not enough to deduce either CH or its negation. 

### References

1. [Lecture Notes by Professor Krishna Jagannathan, IIT Madras](https://www.ee.iitm.ac.in/~krishnaj/EE5110_files/notes/lecture3_cardinality.pdf)
2. [*Principles of Mathematical Analysis* by Walter Rudin](https://web.math.ucsb.edu/~agboola/teaching/2021/winter/122A/rudin.pdf)
3. A bunch of Quora posts by [Alon Amit](https://www.quora.com/profile/Alon-Amit)
4. [Good Ol' StackExchange](https://math.stackexchange.com/questions/189471/why-is-the-continuum-hypothesis-not-true)