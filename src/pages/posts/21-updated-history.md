---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Goodfellow (GBC) Chapter 6'
pubDate: 2023-10-28
description: 'Historical notes from GBC esp. 1980s onwards Chapter 6, esp. Section 6.6'
author: 'Jeff'
image:
    url: ""
    alt: ""
tags: []
---


**Deep Learning (2016)** 
* Ian Goodfellow, Yoshua Bengio, and Aaron Courville
* GBC
## Chapter 6: Deep Feedforward Networks p. 163
### Section 6.6: Historical Notes p. 220
* 'Feedforward networks can be seen as eﬃcient nonlinear function approximatorsbased on using gradient descent to minimize the error in a function approximation.From this point of view, the modern feedforward network is the culmination ofcenturies of progress on the general function approximation task.
* From Leibniz (1676) and L’Hôpital (1696), the calculus chain-rule that underlies backprop was invented in the 1600s. 
* 'Calculus and algebra have long been used to solve optimization in the closed form.' But gradient descent was not introduced as a technique for iteratively approximating the solution numerically (not analytically) until Cauchy (1847) and others in the mid-19th century.' p. 221
* 'Beginning in the 1940s, these function approximation techniques were used to motivate early machine learning models such as the perceptron. However, the earliest models were based on linear models.
* 'Critics including Marvin Minsky pointed outseveral of the ﬂaws of the linear model family, such as its inability to learn the XOR function, which led to a backlash against the entire neural network approach.
* 'Learning nonlinear functions required the development of the MLP (multilayer perceptron) plus the computing resources to compute a gradient through them.'
* 'Efficient applications of the chain rule based on dynamic programming began to appear in the 1960s and 1970s, mostly for control applications but also for sensitivity analysis.
* 'Werbos (1981) proposed applying these techniques to training ANN artificial neural networks.
* Various people rediscovered and put into practice within silicon: Yann LeCun (1985), Parker (1985), the *Nature* article 'Learning representations by back-propogating errors' by Rumelhart, Hinton, and Williams (1986)
* 'Parallel Distributed Processing' by Rumelhart, McClelland, and the PDP Research Group (1986) was a critical book. In the chapter 'Learning internal representations by error propagation' by Rumelhart, Hinton, and Williams, the results of these early successes with backpropagation popularized these technique more broadly.
* The ideas put forward the PDP book, esp. those of Rumelhart and Hinton, go much beyond backprop. They include crucial ideas about the possible computational implementation ofseveral central aspects of cognition and learning, which came under the name *connectionism* because of the importance this school of thought places on theconnections between neurons as the locus of learning and memory.
