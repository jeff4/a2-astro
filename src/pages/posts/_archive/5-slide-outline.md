---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Slides'
pubDate: 2023-10-14
description: 'Outline for Nueva MC slides'
author: 'Jeff'
image:
    url: ""
    alt: ""
tags: []
---

***

## Design
* Background: simple color fill. 2nd column, 1 up from bottom. Transparency at 5%
* Font: Gill Sans MT
	* Font color. Default will be white. Yellow highlights will have black text 

## What we are going to do today
* Explain a bit about what the heck ChatGPT and where it came from
* Hands-on adjust a sort of dumb "untrained" model within the 2 hours to (possibly) outperform the state of the art.
* Give you historical context and some architectural understanding of what's going on




## What you will need
* Laptop with internet connectivity
* Google Account
* Create a HuggingFace account


## Interactive questions
* Who here knows what the GPT in chat gpt stands for?
* Can we come up with a better analogy than this? We are creating unformed beings in the initial pre-training. For the latter-stage fine-tuning, we optimize this being for specific jobs
	* e.g., how about we used to have to build things in a monolithic way before separating out the networking layers per the OSI model?
	* microservices vs. monolithic architecture
	* the internet, the end to end argument? dumb network, intelligent end-applications. This is not the way AOL or the envisioned Information Superhighway was imagined. Unix as a loosely coupled set of small tools each optimized to a single task
	* General purpose computer    







## Timeline
* Neural Networks go back to the 1940s, 'AI' to the Dartmouth conference in the 1950
* 'Winter is Coming'... Game of Thrones. multiple AI winters
* Important work was done in NNs in the 1980s, Development of backprop, application of backprop to CNNs by LeCun
* late 1990s, when google co-founders were in graduate school at Stanford, the "neural network approach" was considered dead. was mostly a 'research backwater' for more than 10 years
* 2006 Deep Belief Networks (probably leave this out)
* **2012** AlexNet / ImageNet
* 2014 GANs (probably leave this out)
* **Dec 2017** Attention is All you Need
* 2018 BERT (probably leave this out)
* **2018 GPT-1 paper.** "Improving Language Understanding by Generative Pre-Training".
	* Good info on [Wiki article](https://en.wikipedia.org/wiki/GPT-1)
	* [PDF link](https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf)
* **2019 release of GPT2.** 
	*Early version in March and [Verge article](https://www.theverge.com/2019/2/14/18224704/ai-machine-learning-language-models-read-write-openai-gpt2) by James Vincent held back full release. But full release came in November 2019.
	* [PDF link](https://cdn.openai.com/better-language-models/language_models_are_unsupervised_multitask_learners.pdf) of original 2019 Radford et al GPT2 paper 'Language Models are Unsupervised Multitask Learners'.
	* [Wikipedia article on GPT2](https://en.wikipedia.org/wiki/GPT-2) is quite good.
* **2020 release of GPT3**
	*  [Wiki article](https://en.wikipedia.org/wiki/GPT-3)
	* 2020 paper 'Language Models are Few-Shot Learners' by Brown, Mann, et al is the GPT-3 paper. Wiki article also mentions the fine-tuned InstructGPT.
* **2022 paper on InstructGPT**
	* 'Training language models to follow instructions with human feedback'
	* [arXiv link](https://arxiv.org/abs/2203.02155)
* **November 2022** - Chat GPT is launched
* **July 2023** - Llama 2 is launched


## Survey / review papers
* 'A Complete Survey on Generative AI (AIGC): Is ChatGPT from GPT-4 to GPT-5 All You Need?' by Zhang, Zhang, et al (March 2023). [arXiv link](https://arxiv.org/abs/2303.11717) and [PDF](https://arxiv.org/pdf/2303.11717.pdf).
	* Organization of types of architecture p. 8
	* Transformer architecture p. 10
	* BERT architecture p. 12 Notice pre-training and fine-tuning diagrams here
	* Masked autoencoder (MAE) p. 13
	* 3 steps of ChatGPT construciton p. 18
* 'Generative Pre-trained Transformer: A Comprehensive Review on Enabling Technologies, Potential Applications, Emerging Challenges, and Future Directions', May 2023. [arXiv link](https://arxiv.org/abs/2305.10435) and [PDF](https://arxiv.org/pdf/2305.10435.pdf).
	* p. 10 - Fig 4 Tranformer architecture and fine-tuning
	* p. 10 - Fig 5 3 step process of supervised fine tuning, reward model, Proximal Policy Optimization PPO reinforcement learning


## Antecedents in Computer History
* Semiconductors in the early 1950s-late 1960s
* PCs in the late 1970s - mid 1980s
* Web 1.0 from 1993 - 2001. 
