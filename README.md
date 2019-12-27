# Bayesian Optimization of Gaussian Processes with Applications to Performance Tuning

## Motivation

The author is a Java Virtual Machine (JVM) engineer. He doesn't know deeply machine learning, but he is interested at optimizing JVM processes.
His motivation is the Twitter microservices, which are coded in Java/Scala (both JVM languages). If the process is not somehow optimized, the energy cost is huge, since servers tend to heat the environment and it is needed coolers to keep the system.

However, we can think of JVM as a composition of several layers. The hardware is the top layer, and each layer has its parameters. Thus, tuning JVM is really hard. There are a lot of parameters and combinations to test, and that makes the problem really hard or even impossible to be solved. Thus, every time someone tries to change JVM design, this person has to make a lot of implementation choices.

## Models

In few words, what we want is to optimize a function, called an objective function, with respect to some parameters. We add some constraints in order to maintain the solution inside a finite range. The difference is that the function is unknown. The author calls that an black-box modelling.

How do we model the function? We use our observations to do that. For example, we have a linear function with only one parameter. The process is to fit a line with my obsevations in order to optimize some critherion (maximum likehood,minimum deviation, etc). If we get more points, then the process is done all over again. 

This model is known as a parametric model. What we are going to use, however, is a non-parametric model. That second model is superior in the sense that it doesn't suffer from overfitting, it is capable of adjusting and scalling as we give more data to it. 

The real problem is the uncertainty. There are two main sources: 

* we don't know the shape of the function. The idea here is to use probabilistic models to measure the uncertainty. Even
though we've made a measurement at two different points, we have some uncertainty about what the shape of the function is in between, and so we allow for that uncertainty. 

* Another other source of uncertainty is the noise. Our data might have some noise.

## Gaussian Processes

There are two interpretations of a Gaussian Process:

* A vector of uncountably many gaussian variables with given mean and joint covariate distribution. 

* A distribution over functions.


In the noiseless case, those values are actually the true values of the objective function.
