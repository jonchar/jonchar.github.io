---
layout: post 
title:	"Python 3.5 matrix multiplication"
date: 	2015-10-13
tags: 	[python3]
---

I'm excited to hear that Python 3.5 has finally added an [operator to handle
matrix multiplication](https://docs.python.org/3/whatsnew/3.5.html#whatsnew-pep-465).
Why you ask? Because I no longer have to call `np.dot()` every time I want to
multiply two matrices. I can now use the new `@` operator to multiply matrices.
`A @ B` looks a lot nicer than `np.dot(A, B)` or `A.dot(B)` and will make
it much more pleasant to write code that performs linear algebra. Python 3.5
has finally arrived in the official [Arch Linux repos](https://www.archlinux.org/packages/extra/x86_64/python/)
and I'm excited to get started using it.

I will surely be using this in the next notebook addition to
[ml-python](http://github.com/jonchar/ml-python/), which will be a [Support
Vector Machine](https://en.wikipedia.org/wiki/Support_vector_machine).
