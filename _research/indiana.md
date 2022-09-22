---
title: "Vector-based Navigation in Artificial Agents"
collection: research
permalink: /research/indiana
excerpt: 'My remote internship at Indiana University Bloomington in the summer of 2021'
date: 2021-05-15
---

During the summer following my sophomore year at IITB, I interned remotely with Prof. [Zoran Tiganj](https://homes.luddy.indiana.edu/ztiganj/) ([Indiana University Bloomington](https://www.indiana.edu/)) on the problem of vector-based navigation in artificial agents. During the course of my internship, I trained an artificial agent to perform path integration and spatial navigation in a 2D environment, with the help of a recurrent neural network. The recurrent cell activities of the trained agent indicated the emergence of grid cells and place cells, which were similar to the neuronal activities observed in the mammalian entorhinal cortex while navigating. Thus, this result helped empirically support neuroscientific theories about spatial navigation in mammals. In the latter half of my internship, I also played around with the architecture of the neural network for solving the problem. This included replacing the recurrent neural network with a long short-term memory network (LSTM), training on polar coordinates rather than Cartesian coordinates, adding multiple layers to the neural network, as well as changing the size of the environment itself. Mixing and matching these changes was a fruitful exercise in experimentation and has taught me persistence and patience. 

I have also written a [blogpost](https://summerblog.insightiitb.org/ishan-kapnadak-indiana-university/?fbclid=IwAR3tzGCf4NAQVhG5W0cWoEF9v87TL0gvb8rh0jB3cF1wg8IS5hmyAf4-tZc) talking about my experience. You can also find some of my work on the project [here](https://github.com/ishankapnadak/Vector-Based-Navigation).