# Cartouche d'identification

* pseudo github : vitorbordini

* Title : Bayesian Optimization of Gaussian Processes with Applications to Performance Tuning

* Manifestation : Qcon

* Lieu : Sao Paulo 

* Conférencier : Ramki Ramakrishna (https://www.linkedin.com/in/ysramakrishna)
 
# Support

* Link : https://www.infoq.com/presentations/bayesian-process-performance-tuning/

# Résumé

## Motivation

The objective is to optimize JVM processes, e.g, a model function. Otherwise, the energy cost is huge. However, JVM has a lot of parameters, wihch makes the problem hard.

## Models

That function is unknown. We use our observations to model it.

This model is a parametric model. It is more interesting, however,a non-parametric model. That second model is superior in the sense that it doesn't suffer from overfitting. 

The real problem is the uncertainty. There are two main sources: 

* Function shape.

* Noisy data.

## Gaussian Processes

A Gaussian Process can be seen as:

* Gaussian variables vector. 

* Distribution over functions.

The Gaussian Process is as follows: From selected points, we draw a curve following a gaussian distribution. We then pick up others points, and redo the process. For every draw, we end up getting a curve that passes through these points.

## Acquisition Functions

We look at two things after the gaussian process:

* Point that optimizes. Figure 1 ilustrates functions drawn from 8 points. If we pickup one function, it tells us that it has the best value at this point, that's where we'll sample. 

![Multiple acquisition fucntions](acquisition.png)

* Probability of improvement. We pick up a point to sample where that probability is maximized.
