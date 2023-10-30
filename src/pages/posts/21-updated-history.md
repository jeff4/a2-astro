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
* 'Feedforward networks can be seen as eﬃcient nonlinear function approximatorsbased on using gradient descent to minimize the error in a function approximation. From this point of view, the modern feedforward network is the culmination of centuries of progress on the general function approximation task.

#### Calculus in the 1600s, Cauchy approximations in the 1800s
* From Leibniz (1676) and L’Hôpital (1696), the calculus chain-rule that underlies backprop was invented in the 1600s. 
* 'Calculus and algebra have long been used to solve optimization in the closed form.' But gradient descent was not introduced as a technique for iteratively approximating the solution numerically (not analytically) until Cauchy (1847) and others in the mid-19th century.' p. 221
* 'Beginning in the 1940s, these function approximation techniques were used to motivate early machine learning models such as the perceptron. However, the earliest models were based on linear models.
* 'Critics including Marvin Minsky pointed outseveral of the ﬂaws of the linear model family, such as its inability to learn the XOR function, which led to a backlash against the entire neural network approach.
* 'Learning nonlinear functions required the development of the MLP (multilayer perceptron) plus the computing resources to compute a gradient through them.'
* 'Efficient applications of the chain rule based on dynamic programming began to appear in the 1960s and 1970s, mostly for control applications but also for sensitivity analysis.
* 'Werbos (1981) proposed applying these techniques to training ANN artificial neural networks.

#### Popularization of backpropagation in the 1980s
* Various people rediscovered and put into practice within silicon: Yann LeCun (1985), Parker (1985), the *Nature* article 'Learning representations by back-propogating errors' by Rumelhart, Hinton, and Williams (1986)
* 'Parallel Distributed Processing' by Rumelhart, McClelland, and the PDP Research Group (1986) was a critical book. In the chapter 'Learning internal representations by error propagation' by Rumelhart, Hinton, and Williams, the results of these early successes with backpropagation popularized these technique more broadly.
* The ideas put forward the PDP book, esp. those of Rumelhart and Hinton, go much beyond backprop. They include crucial ideas about the possible computational implementation ofseveral central aspects of cognition and learning, which came under the name *connectionism* because of the importance this school of thought places on theconnections between neurons as the locus of learning and memory.
* A key idea was the notion of **distributed representation** in an important chapter in the PDP book by Geoff Hinton and [Terry Sejnowski](https://en.wikipedia.org/wiki/Terry_Sejnowski) (Princeton, Johns Hopkins, CalTech, Salk Institute). Co-invention of the Boltzmann machine, and his PhD advisor was John Hopfield of the ['Hopfield Network'](https://en.wikipedia.org/wiki/Hopfield_network). 'Learning and relearning in Boltzmann machines', from Vol 1., Chapter 7 p. 282-317 of *Parallel Distributed Processing*
* Following the success and popularity of the backprop algorithm in the mid-1980s, neural network research gained momentum and reached a peak of AI spring in the early 1990s. 
* 'Afterwards, the AI winter returned for neural networks and other machine learning techniques became more popular until the modern deep learning renaissance that began in 2006 with deep belief networks.'
* GBC: 'The core ideas behind modern feedforward networks have not changed substantially since the 1980s. p.221
	* The **same** back-propagation algorithm and the **same approaches to gradient descent** are still in use. 
	* Most of the improvement in neural network performance from 1986 to 2015 can be attributed to two factors. 
		1. First, larger datasets have reduced the degree to which statistical generalization is achallenge for neural networks.
		1. Second, neural networks have become much larger, because of more powerful computers and better software infrastructure.

#### 1990s–late 2000s: small changes from Cross-Entropy Loss and ReLUs
*A small number of algorithmic changes have also improved the performance of neural networks noticeably. p.222*

##### Rise of Cross-Entropy Loss
* 'One of these algorithmic changes was the replacement of mean squared error with the **cross-entropy family of loss functions**.
	* Mean squared error was popular in the 1980s and 1990s but was gradually **replaced by cross-entropy losses** and the **principle of maximum likelihood** as ideas spread between the statistics communityand the machine learning community. 
	* The use of cross-entropy losses greatly improved the performance of models with sigmoid and softmax outputs, which had previously suﬀered from saturation and slow learning when using the mean squared error loss.

##### Rise of Rectified Linear Units
* 'The other major algorithmic change that has greatly improved the performance of feedforward networks was the replacement of sigmoid hidden units with piecewise linear hidden units, such as rectiﬁed linear units. 
* JH: Before the rise of ReLU, *sigmoid functions* were used for the neurons in the hidden layers. For example, logistic / sigmoid activation functions.
* 'Rectiﬁcation using the `max{0,z}` function was introduced in early neural network models and dates back at least as far as the cognitron and neocognitron (Fukushima, 1975, 1980). 
* 'These early models [from the 1970s] did *not* use rectiﬁed linear units but instead applied rectiﬁcation to *nonlinear functions*.
* 'Despite the early popularity of rectiﬁcation, it was largely replaced by sigmoidsin the 1980s, perhaps because sigmoids perform better when neural networks are very small. 
* 'As of the early 2000s, rectiﬁed linear units were avoided because of a somewhat superstitious belief that activation functions with nondiﬀerentiable points must be avoided. 
* 'This began to change in about 2009. Jarrett et al. (2009) observed that “using a rectifying nonlinearity is the single most important factor in improving the performance of a recognition system,” among several diﬀerent factors of neural network architecture design.'
* 'For small datasets, Jarrett et al. (2009) observed that using rectifying non-linearities is even more important than learning the weights of the hidden layers.
* 'Random weights are suﬃcient to propagate useful information through a rectiﬁed linear network, enabling the classiﬁer layer at the top to learn how to map diﬀerent feature vectors to class identities.'
* 'When more data is available, learning begins to extract enough useful knowledgeto exceed the performance of randomly chosen parameters. Glorot et al. (2011a) showed that learning is far easier in deep rectiﬁed linear networks than in deepnetworks that have curvature or two-sided saturation in their activation functions.'
* 'Rectiﬁed linear units are also of historical interest because they show thatneuroscience has continued to have an inﬂuence on the development of deeplearning algorithms. Glorot et al. (2011a) motivated rectiﬁed linear units from biological considerations.
* The half-rectifying nonlinearity was intended to capture these properties of biological neurons: (1) For some inputs, biological neurons are completely inactive. (2) For some inputs, a biological neuron’s output is proportional to its input. (3) Most of the time, biological neurons operate in the regime where they are inactive (i.e., they should have sparse activations).

#### From 2006 onwards starting with Deep Belief Networks
* 'When the modern resurgence of deep learning began in 2006, feedforward networks continued to have a bad reputation. From about 2006 to 2012, it was widely believed that feedforward networks would not perform well unless they were assisted by other models, such as probabilistic models. 
* 'It is now known that with the right resources and engineering practices, feedforward networks perform very well. Today, gradient-based learning in feedforward networks is used as a tool to develop probabilistic models, such as the variational autoencoderand generative adversarial networks, described in Chapter 20. 
* 'Rather than being viewed as an unreliable technology that must be supported by other techniques, gradient-based learning in feedforward networks has been viewed since 2012 as a powerful technology that can be applied to many other machine learning tasks. 
* 'In 2006, the community used unsupervised learning to support supervised learning, and now, ironically, it is more common to use supervised learning to support unsupervised learning. Feedforward networks continue to have unfulﬁlled potential. 
* 'In the future, we expect they will be applied to many more tasks, and that advances in optimization algorithms and model design will improve their performance even further. This chapter has primarily described the neural network family of models. In the subsequent chapters, we turn to how to use these models--how to regularize and train.'

