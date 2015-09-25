---
layout:	post
title:	"An artificial neural network in Python"
date:	2015-09-24
tags:	[supervised learning, artificial neural networks]
---

The next addition to my collection of learning algorithms implemented
in Python is an [artificial neural network](/notebooks/Artificial-Neural-Network).
I spent a bit more time implementing this one compared to the others
for a few reasons:

1. I wanted to make the code as modular as I could while still illustrating
the basic concepts of forward propagation and back propagation.
Artificial neural networks are by definition made up of many repeating structures, so it makes sense to me to take a similar approach when implementing one. It also makes the code easily re-usable.

2. I tried to vectorize many of the algorithms rather than relying on for loops.
This makes many of the operations much faster by using numpy arrays and in my
opinion makes the code cleaner and less verbose.

3. As I was working out the implementation, I was initially using the same
test data as I did for my [logistic regression notebook](/notebooks/Logistic-Regression)
and was not having much success with fitting the neural network model as I
present it in the notebook. After re-reading some notes, I tried a different
data set centered roughly around zero and this worked much better. I could
probably have normalized it, but then I came across [this post by Denny Britz](http://www.wildml.com/2015/09/implementing-a-neural-network-from-scratch/)
that uses scikit-learn's [`make_moons`](http://scikit-learn.org/stable/modules/generated/sklearn.datasets.make_moons.html#sklearn.datasets.make_moons)
dataset generator, which I thought was pretty cool so I decided to try it out
with my impementation. Lo and behold, my implementation was able to fit the
zero-centered generated data much easier.

If you'd like to follow along with the implementation you can find a
jupyter notebook with the code and associated math in my [ml-python repo](http://github.com/jonchar/ml-python)
or read it rendered in HTML here:

**[Artificial neural network in Python](/notebooks/Artificial-Neural-Networks)**
