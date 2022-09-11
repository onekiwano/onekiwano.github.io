---
layout: page
title: About me
permalink: /about/
image: /assets/article_images/about/author_full.jpg
---

## Summary
*Thesis title* : From circuit to dynamics and performance in tasks, how to design spiking neural networks reservoir without plasticity?

Ph.D student in Electrical and computing engineering (Université de Sherbrooke).

- Director : Jean Rouat (NECOTIS)
- Co-director : Bertrand Reulet (IQ)

## Introduction
I am a Ph.D. student at the intersection of three disciplines: computational neurosciences, artificial intelligence, and physics. My goal is to use physics concepts to understand better and design machine learning models.

I am working in the field of reservoir computing. It is a niche branch of artificial intelligence compared to ubiquitous deep learning and artificial networks. Still, it is very promising, especially when considering the intrinsic limitations of these techniques: computational and energy cost.

Deep networks are run on giant GPU clusters, extraordinarily costly in technology, power consumption [1], and ecological impact [2]. It is striking that our brains only cost 10 to 25 watts while being able to perform probably more than 10^15 flop operations [3] ! ... e.g., we have a vast room for improvement! Moreover, not only is energy scarce, but resources are too, while most of our digital techs rely on rare metals, primarily found in China's mines [4]. You have a pretty fragile interdependence chain, subject to many issues, ranging from political to climatic, and well, now we'd have to add sanitary to this non-exhaustive list!

In that context, I see reservoir computing as a serious concurrent for building extremely cheap and potentially eco-friendly computational devices. You will understand why in a second after I show you what it is!

So let's see how it can work:

1. Take a bucket of water.
2. Take a camera looking at the surface of the water.
3. Take a computer program analyzing the camera output.
4. Now drop things into the buckets, ...
5. Have fun!

![Taken from [5].](/assets/article_images/about/pic0.png)

Tadaa! There you are, you have a computational device, ready to classify various input data and capable of performing computation!

You don't believe me ?! Check this out [6]; this is a 2003 study, they performed an XOR function with a simple bucket of water, and of course, a computer executing an analysis of the wave's patterns at the water's surface!

![Taken from [5].](/assets/article_images/about/pic1.png)

## AI or not AI, that is the question!
Right now, you should be wondering what on earth am I doing concretely? Am I playing with weird physical systems to perform computation ? ...

![Physical systems used as an actual reservoir.](/assets/article_images/about/pic2.png)

Well, not really, and before everyone carries their computer within their bottle of water, I'd like to say there is still a lot of ongoing improvement with neural networks. The next evolution in AI is currently spiking neural networks. No wonder since they are mimicking real biological ones. They use current only during the short electrical discharge called "action potential," while their favoured state is silence. The significant advantage is that information can be encoded in the time between spikes, the interval of silence between discharges. This is a drastic advantage over the ANN that encodes for the rate of discharge in time, which means they require current at each time step!

Now I've given two, and I believe good reasons, to study reservoir computing with spiking neural networks.

## The actual real question I am asking
Well, before even creating an actual physical substrate for a reservoir, we decided to perform a theoretical and simulation-based study of how to design a good network of spiking neural networks for different types of computational tasks.

My central questions are the following :

- How to design a spiking neural network optimally tuned to some specific tasks giving the best performances without any plasticity mechanism in the reservoir?
- And the corollary, how to design a reservoir that would be optimally tuned to solve many tasks while not necessarily being the most accurate in specific tasks?

### And how?

So for those how are not familiar with AI, this question can seem a little bit abstract, and I will explain to you what it means and even how this question is pertinent in AI :

### 1. Design of spiking neural networks
First off, we must understand what is meant by designing a spiking neural network. There are many possible ways of seeing this, but I will narrow it down to two essential parts :

- You have an architecture, a directed graph, with nodes and edges. (We call them neurons and synapses.)
- You have weighted edges, also called synaptic weights, that act as amplification and or inhibitions of the input received from other neurons via the edges.

#### Problematic :

Most studies in reservoir computing generate circuits randomly. Many papers studied the dynamics associated with architectures, such as small-world and scale-free topologies. On the other hand, the impact of the initialization of weights matrices is still poorly understood.
- In fact, most weight matrices are initialized randomly with very high variability in obtained results!

NB: Many more elements are to be considered, such as the equation of the neuron, the non-linearity, the threshold, and much more. To reduce complexity, I decided to use the simplest neural model that possesses none of these parameters, the **binary neural model**.

### 2. Plasticity
Second, plasticity is everywhere in neural networks; it is the Sacro-saint principle behind any classification and regression in deep learning, ANN, LSTM... This is a consequence of 40 years of thriving neurosciences, showing how everything is plastic *in vitro* and *in vivo*; circuitry, neurons and synapses are constantly adapting.

#### Problematic :

One of the common problems in reservoir computing is the random search of the weights matrices. To avoid that, people tended to use learning update rules. However, learning takes time, energy, and a lot of work to design and know what learning rules to apply with which parameters. 

However, reservoirs do not need learning if they are appropriately initialized. Thus, using learning rules seems counterproductive and removing one of the reservoirs' initially exciting features: it is inherently computationally rich. e.g. you don't have to train a bucket of water!

According to the ground principle in physics, if you can reproduce a result with less complexity in your model/computational system, you probably found a better one. Hence the question, is plasticity always necessary?

> Practically, can we design a reservoir of spiking neurons without the use of plasticity?

## What do I do?
My thesis will try to answer these questions by exploring many instantaneous weights matrices initialization and giving a systematic link between circuit properties, dynamics, and performance in specific tasks.

## Where am I right now?
I am writing my first paper. We have decent results, and we are almost done with experiments; soon enough, I will submit it for peer review!

## References
[1] https://www.openphilanthropy.org/blog/new-report-brain-computation

[2] https://analyticsindiamag.com/deep-learning-costs-cloud-compute/

[3] https://towardsdatascience.com/compute-and-environmental-costs-of-deep-learning-83255fcabe3c

[4] https://www.azomining.com/Article.aspx?ArticleID=49

[5] Kohei Nakajima, Physical reservoir computing—an introductory perspective, 2020 Jpn. J. Appl. Phys. 59 060501

[6] C. Fernando and S. Sojakka, Lecture Notes in Computer Science 2801 (Springer, Berlin, 2003), p. 588.

