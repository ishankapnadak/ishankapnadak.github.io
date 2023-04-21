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
### The $(4,3)$ polyrhythm
These are the easiest kind of polyrhythms to play. Here, we just take $a = 4$. The first polyrhythm we consider is the $(4,3)$ polyrhythm. The way to do this is actually quite straightforward. We basically start with $3$ quarter notes, where each is grouped into $4$ sixteenth notes (remember the $1$, $e$, $\&$, $a$ stuff?), and we place these groups of sixteenth notes one on top of the other. Something like this:

$$ 1 \quad e \quad \& \quad a \\
2 \quad e \quad \& \quad a \\
3 \quad e \quad \& \quad a$$

Now, to play the $3$ part of our polyrhythm, we simply play the first note of each group (note that there are $3$ of them, each of the same duratoin). Let's highlight these in blue (since the $3$ is our "blue" note). We now have 

$$ \textcolor{blue}{1} \quad e \quad \& \quad a \\
\textcolor{blue}{2} \quad e \quad \& \quad a \\
\textcolor{blue}{3} \quad e \quad \& \quad a$$

Now, to play the $4$ part of our polyrhythm - we have a total of $12$ sixteenth notes to work wth. Since we want to divide this into $4$ equal parts, each part occupies $3$ sixteenth notes. (It is interesting to see that the numbers somehow switched up - each $4$-division occupies $3$ blocks and each $3$-division occupies $4$ blocks). Thus, starting at $1$, we color every $3^{\text{rd}}$ note with the color red (since the $4$ is our "red" note). The first note appears in both the sequences, so let's just color it pink. We have

$$ \textcolor{fuchsia}{1} \quad e \quad \& \quad \textcolor{red}{a} \\
\textcolor{blue}{2} \quad e \quad \textcolor{red}{\&} \quad a \\
\textcolor{blue}{3} \quad \textcolor{red}{e} \quad \& \quad a$$

And there we have it - our $(4,3)$ polyrhythm! There are a lot of cool demonstrations of this polyrhythm online that are worth checking out. [Here](https://www.youtube.com/shorts/DuG0oAEF2hE) is one! A couple of things to note:
1. The $1$ is the only note that coincides in the entire pattern (this is a coincidence of $3,4$ being coprime)
2. The $4$ notes being played as part of the $4$-rhythm are exactly the first, second, third, and fourth sixteenth notes but permuted (note that we play the $1$, the $e$ of the $3$, the $\&$ of the $2$, and the $a$ of the $1$). This will be the case for all polyrhythms involving $4$! 

### The $(4,5)$ polyrhythm

Let's step things up to the $(4,5)$ polyrhythm. This is a slightly harder polyrhythm since it's longer. But we follow the same procedure as before! We start with $5$ quarter notes, with each divided into $4$ sixteenth notes. This gives us:

$$ 1 \quad e \quad \& \quad a \\
2 \quad e \quad \& \quad a \\
3 \quad e \quad \& \quad a \\
4 \quad e \quad \& \quad a \\
5 \quad e \quad \& \quad a$$

As before, we color all the numbers with a blue since these are precisely the "blue" notes in our pattern - 

$$ \textcolor{blue}{1} \quad e \quad \& \quad a \\
\textcolor{blue}{2} \quad e \quad \& \quad a \\
\textcolor{blue}{3} \quad e \quad \& \quad a \\
\textcolor{blue}{4} \quad e \quad \& \quad a \\
\textcolor{blue}{5} \quad e \quad \& \quad a$$

For the $4$ part, we now start with the $1$ and color every *fifth* note red. This gives us

$$ \textcolor{fuchsia}{1} \quad e \quad \& \quad a \\
\textcolor{blue}{2} \quad \textcolor{red}{e} \quad \& \quad a \\
\textcolor{blue}{3} \quad e \quad \textcolor{red}{\&} \quad a \\
\textcolor{blue}{4} \quad e \quad \& \quad \textcolor{red}{a} \\
\textcolor{blue}{5} \quad e \quad \& \quad a$$

And we have our $(4,5)$ polyrhythm! Put in words, you play each quarter note, the $e$ of the $2$, the $\&$ of the $3$, and the $a$ of the $4$! Again we observe that $4$ red notes being played are $1,e,\&,a$. Moreover, they appear in order this time - that is the $1$ is played first, followed by the $e,\&,a$ in order. Recall that $(4,3)$ had the reverse order! We played the $1$ first, followed by the $e,\&,a$ in reverse order. As we shall see soon - these are the only two patterns we really need to remember. Let us go a step further!

### The $(4,7)$ polyrhythm

This is an even longer polyrhythm, occupying $7$ quarter notes! We have

$$ 1 \quad e \quad \& \quad a \\
2 \quad e \quad \& \quad a \\
3 \quad e \quad \& \quad a \\
4 \quad e \quad \& \quad a \\
5 \quad e \quad \& \quad a \\
6 \quad e \quad \& \quad a \\
7 \quad e \quad \& \quad a$$

As before, we color all the numbers with a blue since these are precisely the "blue" notes in our pattern - 

$$ {\color{blue}{1}} \quad e \quad \& \quad a \\
\textcolor{blue}{2} \quad e \quad \& \quad a \\
\textcolor{blue}{3} \quad e \quad \& \quad a \\
\textcolor{blue}{4} \quad e \quad \& \quad a \\
\textcolor{blue}{5} \quad e \quad \& \quad a \\
\textcolor{blue}{6} \quad e \quad \& \quad a \\
\textcolor{blue}{7} \quad e \quad \& \quad a$$

For the $4$ part, we now start with the $1$ and color every *seventh* note red. This gives us

$$ \textcolor{fuchsia}{1} \quad e \quad \& \quad a \\
\textcolor{blue}{2} \quad e \quad \& \quad \textcolor{red}{a} \\
\textcolor{blue}{3} \quad e \quad \& \quad a \\
\textcolor{blue}{4} \quad e \quad \textcolor{red}{\&} \quad a \\
\textcolor{blue}{5} \quad e \quad \& \quad a \\
\textcolor{blue}{6} \quad \textcolor{red}{e} \quad \& \quad a \\
\textcolor{blue}{7} \quad e \quad \& \quad a$$

Notice that the order of the red notes is now flipped again! This pattern is actually very similar to the $(4,3)$ pattern - it's in fact the same pattern of red notes with an additional quarter note space between each red note! This is not surprising since $7 = 3 + 4$ (hmm okay how does this help?) Let's go the distance and generalize this!

### Generalizing the $(4,n)$ polyrhythm

Since $\text{gcd}(4,n) = 1$, we have only two cases
1. $n = 4k + 1$ where $k > 0$, and
2. $n = 4k+3$ where $k \geq 0$. 