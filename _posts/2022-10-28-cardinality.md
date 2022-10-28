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

### Comparing Cardinalities of two sets

We assume that the reader is familiar with common notions in set theory (in particular, the reader is hopefully familiar with the notion of sets, their unions and intersections, functions, their injectivity, surjectivity, and bijectivity). Georg Cantor came up with the idea of using functions between sets to compare their cardinalities. For example, if we are able to find a bijection between two sets, it must be the case that they have the same ''number'' of elements, that is, they are equicardinal. Similarly, if we are able to find an injection from one set into another, it must be the case that the latter set has ''at least as many elements'' as the former. These notions are formalized as follows.

1. Two sets $$A$$ and $$B$$ are **equicardinal** ($$\levrt A \rvert = \lvert B \rvert$$) if there is a bijection from $$A$$ to $$B$$.
2. $$B$$ has cardinality greater than or equal to $$A$$ ($$\lvert A \rvert \geq \lvert B \rvert$$) if there is an injection from $$A$$ to $$B$$.
3. $$B$$ has cardinality strictly greater than $$A$$ ($$\lvert A \rvert \geq \lvert B \rvert$$) if there is an injection but no bijection from $$A$$ to $$B$$.  