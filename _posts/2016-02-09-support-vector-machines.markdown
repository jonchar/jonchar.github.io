---
layout: post 
title:	"Implementing a support vector machine (SVM) using sequential minimal optimization"
date:	2016-02-09
tags:	[supervised learning, support vector machines, SVM]
---

The last few months have been busy to say the least, there are so many
interesting things I want to learn but there are only so many hours in the
day. One of those things was getting a handle on how to solve the [support
vector machine optimization problem using sequential minimal optimization
(SMO)](/notebooks/SVM). I based my code on the pseudocode presented in the
original paper describing the SMO algorithm by John Platt at Microsoft in 1998.

SVMs differ from the previous supervised learning algorithms I've implemented
in a few ways:

1. The SVM optimization problem is a constrained convex optimization
problem which means our previous approach of finding the derivative of the
cost function and using gradient descent won't work as well. There are many
solvers that will work such as CVXOPT and LIBLINEAR/LIBSVM. Scikit-learn
uses LIBLINEAR/LIBSVM under the hood, which in turn uses an SMO-like algorithm.

2. SVMs can easily make use of kernels, which map input features into a
different space. What this means is that non-linear decision boundaries can be
easily obtained depending on the kernel used. Rather than feature engineering,
one can explore which kernel best lends itself to the data you are modeling.

3. For classification problems, SVMs only weight examples that are close to
the decision boundary. Thus adding new training data far from the boundary
will not change the boundary.

4. Regularization is added via a single parameter C (by convention) and the
degree of regularization is inversely proportional to its magnitude. This is
in contrast to the previous algorithms I've implemented in Python where the
regularization parameter's magnitude and the degree of regularization shared
a direct relationship.

This particular implementation was pretty tricky to get off the ground but I
did eventually get it to work. It doesn't work perfectly, which makes me think
there are a few parts I didn't get quite right. It was a tremendous learning
experience working on this anyway so I'm happy with it.

You can find the Jupyter notebook to follow along with in my [ml-python repo](http://github.com/jonchar/ml-python)
along with the others, and an HTML version [here](/notebooks/SVM).

If you find something wrong in the implementation feel free to contact me with your
feedback!
