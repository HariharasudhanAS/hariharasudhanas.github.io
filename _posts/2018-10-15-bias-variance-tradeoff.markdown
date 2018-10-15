---
layout: post
title: "The Bias-Variance Tradeoff"
date: 2018-10-15
categories:
  - Data-Science
description: Intuitive understanding of the bias variance trade-off
image: https://i.postimg.cc/YCK4WY17/Screenshot-from-2018-10-15-23-28-07.png
image-sm: https://i.postimg.cc/YCK4WY17/Screenshot-from-2018-10-15-23-28-07.png
---
## The Bias-Variance Tradeoff
One of the major aspects of building a machine learning model is the bias-variance tradeoff. You might have come across terms like over-fitting and under-fitting thrown around in the field of machine learning and statistical modeling in general, so what is it? Let's dive in.
### A few things to note before we get to the bias vs variance part:
We take up statistical methods to predict or infer information from data only when we don’t know the actual underlying phenomena. The pure function or in statistical terms, the population function. You cannot model data better than the population function, this much is obvious. But, the real world fails us and just like physicists [https://youtu.be/StHMKdvuHN0], we work with approximations and assumptions to make our work easier. We instead work with sample data drawn from the population which includes noises ( datapoint that doesn’t fit the population function) etc. Our aim is to reduce the total error in a model when the model is applied to unseen data. It might sound like black magic, but it is very much mathematical. 
### What is bias?
Bias according to the Cambridge dictionary:
“is the action of supporting or opposing a particular person or thing in an unfair way, because of allowing personal opinions to influence your judgment.”
Well, that is pretty close to our context. If you as an individual is biased about something, you would not listen to reason or logic that says otherwise. The more biased you are, the less you change. This is very similar to bias in the statistical context.
The error function in the case of linear regresison:
<p align="center"> 
<img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/e5e01509ca06e85039e69a64de77561ecb7c50c0">
</p>
So, the error term consists of bias, variance, and a third term - the irreducible error that is part of the population function. We try to reduce the reducible error to make the model a nice fit. But, making the model better fit the sample data is almost always bad as our aim is to use the model on unseen data. So, imagine yourself to be the model. You encounter a lot of data points (similar to reason or logical arguments in the simple definition of bias), but if you are biased, you are less likely to change from what you think even if the data points otherwise. This is exactly what happens. In linear regression, assuming the relation between the predictors to be linear contributes to bias by itself ( we ignore biasing in the sampling methodology ), and the model isn’t receptive to the data points. 
In the case of KNN classification, let's take by a two-dimensional dataset. Assume yourself to be a point on the plot between the two dimensions. Now, if you are biased in your opinions as to which class you - the point where you are standing belongs, it can be thus inferred that a lot of nearby data points ( or logical reasoning ) that think otherwise are needed to change your opinion about the classification. Thus when K increases, it is the same as the model’s bias increasing.
### Variance
According to Google, Variance is :
“the fact or quality of being different, divergent, or inconsistent.”
In the context of our model, this translates to the model being inconsistent. But inconsistent with what? We build our models on the sample data, and this is a subset of the larget population data. So, there are many sample data sets that could be drawn from the population dataset, and variance is the inconsistency of the model with respect to these various sample datasets. Assume we build a model on sample dataset A, and build it again on sample dataset B with the same assumptions as the earlier model w.r.t type of model, nature of relation etc, the amount of change in the prediction of a data point in the datasets is the variance of the model. Assume the linear regression case, if you had based your model on few predictors, a small change in the predictor values in the next sample dataset will cause a large change in your model. 
The analogy - assume yourself to be the model on a plane that contains a plot between two predictors. Now you have to decide which class the point you are standing on belongs to, and hence assign it according to the opinions of the K nearest data points. Now, suppose you are standing on the same point as before, but a different sample dataset is plotted, you are much more prone to change your stance if your (the model’s) variance is high. 

### Why the trade-off?
Let us take the KNN classification example. You are the model deciding the class the data point you are standing on belongs to. 
Bias - You can be heavily biased or with a low bias. If heavily biased, it would take a lot of nearby data points to change your opinion.
Variance - If you are heavily biased and require a lot of data points nearby to think opposite to your stance, you are unlikely to change much as the sample distributions drawn from the same population distribution are similar. But in the other case, if you require very few data points ( or logical arguments ) to change your stance, with a slight change in the sample distributions, your stance will change making you inconsistent.
Thus, as bias decreases, variance increases. That is, they have an inverse relationship. 
### Conclusion
As a statistical modeler, one’s goal is often to reduce the error on the training (unseen) data. We do this by reducing the sum of the bias and variance term in the error decomposition equation. When the bias is low, we are said to have under-fit the data as the model is not responsive to the data, and over-fitting is when the model has very low bias and thus starts to be responsive to everydata point it comes across - even the noise.  
Just like in real life, being highly biased or highly inconsistent ( variant ) isn’t the best approach to statistically model data. We learn from experience, but not believing everything we come across is also a vital part of learning. This post is more about getting an intuitive understanding than being mathematically correct.   
P.S. This is my first technical blog post. Please reach out to me at harimailbox99 at google’s mail service dot com with any constructive feed back you might have.

