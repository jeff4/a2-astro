---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Notes on RNN, etc.'
pubDate: 2023-10-28
description: 'Two 2014 RNN papers by Cho+Bengio; Goodfellow chapter 10'
author: 'Jeff'
image:
    url: ""
    alt: ""
tags: []
---

***
## Papers
* *Learning Phrase Representations using RNN Encoder–Decoder for Statistical Machine Translation* by Cho, Bahdanau, Bougares, Schwenk, and Bengio 2014a. [arXiv link](https://arxiv.org/abs/1406.1078) and [PDF](https://arxiv.org/pdf/1406.1078.pdf)
* *On the Properties of Neural Machine Translation: Encoder–Decoder Approaches* by Cho, van Merrienboer, Bahdanau, and Bengio 2014b. [arXiv link](https://arxiv.org/abs/1409.1259) and [PDF](https://arxiv.org/pdf/1409.1259.pdf)

***

**Deep Learning (2016)** 
* Ian Goodfellow, Yoshua Bengio, and Aaron Courville
* GBC
## Chapter 10: Sequence Modeling: RNNs and Recursive Nets
* RNNs (first defined by Rumelhart et al, 1986a) are a family of neural networks for processing sequential data. Much as a CNN specializes in a grid of values **`tensor X`** such as a 2-D image, an RNN is specialized at processing a sequence of vectors **v<sub>1</sub>**...**v<sub>n</sub>**. p.367
* Most RNNs can process sequences of variable length.

### Parameter sharing
* Parameter sharing makes it possible to extend and apply the model to exampels of different lengths and generalize across them. Example of 2 different sentences: "I went to Nepal in 2009" vs "In 2009, I went to Nepal". A simple fully-connected feedforward ANN that is trained to discriminate between these two sentences would eventually converge such that all the rules of the language would have to be learned for each word position.
* In contrast, a RNN shares the same parameter weights across several time steps.

### Explanation of why a 1-D CNN is shallow while a RNN is a deeper representation p. 368
* 'A convolution operation allows a CNN to share parameters across time but is shallow.'
* 'The output ofconvolution is a sequence where each member of the output is a function of asmall number of neighboring members of the input.'
* A RNN shares parameters in a different way.
* **'Each member of the output is a function of the previous members of the output.'**
* 'Each member of the output is produced using the same update rule applied to the previous outputs.'

### Unfolding Computational Graphs p.369
* See diagram in JH Comp Notebook #1.
* 'A computational graph is a way to formalize the structure of a set of computations,such as those involved in mapping inputs and parameters to outputs and loss.' p. 369
* General introduction to computational graphs is in Section 6.5.1. 
	* Each **node** in the graph represents a variable. p. 198
		* The variable may be scalar valued, vector-valued, matrix-valued, tensor-valued, or even some other type.    
	* Each **edge** is called an **operation**. An operation is just a simple function that can output a single output variable. Remember, that variable can be tensor of any rank so you can think of it as a multidimensional array of arbitrary rank and dimension. 
	* Generalities that can come from applying the chain rule in calculus.
	* This leads to recursive application of the chain rule to derive the backpropagation algorithm.
* Classical physics model of a very simple dynamic system across time from `t=0`






