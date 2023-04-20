---
title: 'Polyrhythms and Number Theory'
date: 2023-04-21
permalink: /posts/2023/04/polyrhythms/
tags:
  - math
  - number theory
  - music
katex: true
excerpt: ''
---

## What are Polyrhythms?

Polyrhythms are a fairly advanced but commonly used technique in music, usually involving two or more conflicting rhythms playing together. Typically, the simplest polyrhythm involves two positive numbers $a$ and $b$. Each bar or measure (which can be thought of as a single unit of time) is divided in two different ways. We divide each unit into $a$ equal subdivisions (for the more musically inclined, you can think of these subdivisions as being $a$-tuplets). We also divide the same unit into $b$ equal subdivisions (and of course, each subdivision here is a $b$-tuplet). When each of these rhythms is played individually, nothing interesting happens - in the first case, you have $a$ equally spaced notes, whereas in the second case you have $b$ equally spaced notes being played. The magic happens when these two rhythms are played together. Here again, you have a sequence of $a$ equally spaced notes (call these the "red" notes) and a sequence of $b$ equally spaced notes (call these the "blue" notes). However, the duration of each red and blue note is different! Suppose the duration of my unit is $T$. Each red note then occupies a duration of $\frac{T}{a}$, whereas each blue note occupies a duration of $\frac{T}{b}$. We will restrict ourselves to the case where $\text{gcd}(a,b) = 1$ (that is, we consder $a$,$b$ to be co-prime). If $\text{gcd}(a,b) > 1$, it is easy to see that the overall polyrhythmic pattern is just repetitions of a reduced pattern. For example, a $(35,21)$ polyrhythm is just $7$ repetitions of a $(5,3)$ polyrhythm. 

## Polyrhythms with the quarter note

These are the easiest kind of polyrhythms to play. Here, we just take $a = 4$. The first polyrhythm we consider is the $(4,3)$ polyrhythm. The way to do this is actually quite straightforward. If you're a musician, we basically start with $3$ groups of $4$ $16$th notes (remember the $1$, $e$, $\&$, $a$ stuff?), and we place these groups one on top of the other. Something like this:

|   |   |   |   |
|---|---|---|---|
| 1 | e | & | a |
| 2 | e | & | a |
| 3 | e | & | a | 