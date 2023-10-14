---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Glossary for MC'
pubDate: 2023-10-14
description: 'Glossary for Nueva Math Circle'
author: 'Jeff'
image:
    url: ""
    alt: ""
tags: []
---

***

## Primary
* Generative
	* creates images, next tokens, etc.
	* [Wolfram: What is ChatGPT Doing...And why does it work?](https://writings.stephenwolfram.com/2023/02/what-is-chatgpt-doing-and-why-does-it-work/)
	* Temperature range is usually between 0.1 to 2.0
* Pre-Trained
	* short definition from [2016 StackExchange](https://stats.stackexchange.com/questions/193082/what-is-pre-training-a-neural-network) - "Instead of repeating what you did for the first network and start from training with randomly initialized weights, you can use the weights you saved from the previous network as the initial weight values for your new experiment. Initializing the weights this way is referred to as using a pre-trained network. The first network is your pre-trained network. The second one is the network you are fine-tuning."
	* Read the original GPT paper "Improving Language Understanding by Generative Pre-Training" by Radford et al (2018)
	* Sebastian Raschka's [LLM Reading List](https://sebastianraschka.com/blog/2023/llm-reading-list.html) is an essential resource
	* BERT is bidrectional. Encoder only. Better for text classification,  not generation as much
* Transformer - new architecture proposed in a famous paper from Google Brain and Google Research. Involved multiple attention heads and focused on unsupervised training.
	* [Illustrated Transformer](http://jalammar.github.io/illustrated-transformer/) is a good detailed breakdown of Transformer architecture
	* Original transformer both an encoder and decoder parts
	* But GPT is decoder only, as researchers have found that the decoder layers are most useful for generation.
* Large Language Model (LLM)
* LoRA. Also QLoRA
* Quantization
* Supervised Training
* T4 - refers to the NVIDIA T4 Tensor Core GPU that will be using today in the Colab Notebook
* Temperature
* Unsupervised Training
* Vector

***

## Secondary

* Epoch
* Float16
* GPU
* Google Colab
* Hugging Face
* Fine-Tuning
* Float16
* Unsupervised Training
* Vector
* Tensors
* Training Loss
* Training see also supervised training, unsupervised training
* Transformer
* Prompt see also System Prompt `<SYS>` versus User Prompt
* Prompt Engineering
* Python
* Pytorch
* Matrix (matrices is plural)
* PEFT Parameter Efficient Fine-Tuning
* Parameters. Weights and biases
* GPU
* Hugging Face
* Hyperparameters. See [wiki article](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning) as well as Goodfellow GBF textbook definitions. This [Stack Exchange answer](https://datascience.stackexchange.com/a/14234) is pretty good. Also this [Andrew Ng 7-minute video](https://www.coursera.org/lecture/neural-networks-deep-learning/parameters-vs-hyperparameters-TBvb5)
* Inference
* Google Colab
* Instruction [INST]
