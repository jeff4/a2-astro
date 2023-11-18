---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Goodfellow (GBC) Chaps 7,8,9'
pubDate: 2023-11-15
description: 'Selected notes from Chapter 7 (Regularization) and Chapter 8 (Optimization)'
author: 'Jeff'
image:
    url: ""
    alt: ""
tags: []
---

**Deep Learning (2016)** 
* Ian Goodfellow, Yoshua Bengio, and Aaron Courville
* GBC
## Chapter 9: Historical notes from end of CNNs
### 9.11 CNNs and the History of Deep Learning
* CNNs are a key example of a successful application of insights obtained by studying the brain. p. 359
* They were also some of the first deep models to perform well, long before arbitrary deep models were considered viable.
* CNNs were also some of the first neural networks to solve important commercial applications and remain at teh forefront of such applications all the way to day (as of 2016).
* For example, in the 1990s, the neural network research group at AT&T developed a convultional network for reading checks. See Yann LeCun, Bottou, Yoshua Bengio, and Haffner (1998) "Gradient-based learning applied to document recognition." *Proc. IEEE*
	* By the end of the 90s, the CNN developed by LeCun et al at AT&T/Bell Labs was deployed by NEC and was reading more than 10% of all checks in the US.
* See 2003 paper by Simard, Steinkraus, and Platt "Best Practices for Convolutional Neural Nets" in *ICDAR 2003* for more examples of CNNs used for OCR and handwriting recogonition deployed by Microsoft
* For more an in-depth history of CNNs, see 2010 paper by LeCun, Kavukcuoglu, and Farabet "Convolutional networks and applications in vision." *Proceedings of 2010 IEEE ISCAS (International Symposium on Circuits and Systems)*
* CNNs were also used to win many contests. The current intensity of commercial interest in deep learning began when Krizhevsky et al (2012) won the ImageNet object recognition challenge. 
* ...But CNNs had already been used to win other ML and computer vision contests (with less impact) for years earlier.
* CNNs were some of the first working deep networks trained with backprop.
* It's not entirely clear why CNNs succeeded when general back-propagation networks were considered to have failed.
* It may simply be that CNNs were more computationally efficient than fully-connected networks--so it was easier to run multiple experiments with them and tune their implementation and hyperparameters.
* Larger networks also seem to be easier to train.
* With modern hardware, large fully connected networks appear to perform reasonably on many tasks, even when using datasets and activation functions that were available and popular during the earlier times when fully connected networks were believed to not work well.
* Possibly, **the primary barriers to the success of neural networks were *psychological*.** i.e., Practitioners did not expect neural networks to work, so they did not make a serious effort to use neural networks.
* Whatever the case, it is fortunate that CNNs performed well decades ago. **In many ways, CNNs carried the torch for the rest of deep learning** [during the lean years of the ANN winter]. And then, CNNs paved the way to the acceptance of neural networks in general.

## Chapter 7: Regularization for Deep Learning p. 221
* Simply defined, regularization is any technique or process that allows the **reduction of test error** (aka *generalization error* see notes on Chapter 5) while accepting some increase in training error.
* See also Chapter 5 of ISL (Introduction to Statistical Learning 2021 by Tibshirani et al). PDF available in Box
* See also quick overview of Regularization concepts in GBC Section 5.2.2, such as very basic treatment of "generalization, underfitting, overfitting, bias, variance, and regularization." p. 221
	* On GBC p. 107 note that '**generalization error** is exactly synonymous with **test error**' from first page of Section 5.2
* 'Regularization adds terms to the objective function which can be thought of as extra constraints and penalities.
* 'Sometimes these constraints/penalties are meant to improve performance on the test set. 
* 'Sometimes these constraints/penalties **are designed to encode specific kinds of prior knowledge**.
* 'Sometimes these constraints/penalties are meant to improve the generalization of a model so that it does not overfit on a simple objective.
* 'Finally, regularization includes *ensemble methods* which combine multiple hypotheses to explain training data' p.222
* In the context of deep learning, *most regularization strategies are based on regularizing estimators*.
	* **Regularizing an estimator works by trading increased bias for reduced variance.**
	* An effective regularizer is one that makes a profitable trade by significantly reducing variance while not overly increasing bias.
* Per Chapter 5, there were 3 regimes:
	1. Excluding the true data-generating process (aka *underfitting* and *inducing bias*)
	1. Correctly/accurately matching the data-generating process
	1. *Including* the true data-generating process *but* also matching many other generating processes (aka *overfitting*)
		* In this overfitting regime, variance rather than bias dominates the estimation error
* The goal of regularization is to move from the 3rd regime above to the 2nd regime.
* Some archaelogy. **J() = objective function**. From GBC p.79, synonyms for objective function include:
	* **cost function**
	* **loss function**
	* **error function**
* Also from p.79, "We often denote the value that minimizes or maximizes a function with a superscript *. For example, we might say x&#8407;<sup>\*</sup> = arg min f(x&#8407;)." i.e., x&#8407; refers to when f'(x&#8407;) = 0 and there is a minimum in the derivative df/dx.  
* Where is the first instance of theta **&#952;** ?
	* p.119 Point estimation from Section 5.4.1. True value of a parameter is denoted by **&#952;**. In contrast, the *estimate* of the value of the parameter is with **&#952;-hat**. And since both the regular and hat versions of theta are vectors, they can contain many values for the parameter.
	* p.165 Intro to Chap6 on Deep FeedForwward networks. Third of 3 options on mapping of function phi aka &#966;. 'We now have a parameters **&#952;** that we use to learn &#966; from a broad class of of functions. And also a vector w&#8407; that contains all the individual `weight` values that map from &#966;(x&#8407; ) to the final output.' 



##### Double-struck R for Real numbers
* "rp = double-struck R = &#8477; 
* "tp = theta = **&#952;**
* "hp = theta-hat = **&#952;-hat**
* "pp = vector arrow above prior character = &#8407; 
* "yp = lowercase phi = &#966;










## Chapter 8: Optimization for Training Deep Models p. 267
* GBC Chapter 8, section 8.3 is on Stochastic Gradient Descent (SGD)
* AdaGrad and then in section 8.5.3 Adam adaptive learning rate optimization * Batch Normalization is extremely exciting circa 2015 (section 8.7.1) * section 8.7.4 Supervised Pretraining

