---
layout: post
title: "Univariate Linear Regression in SciPy"
date: 2013-01-10
categories: misc
tags: python scipy matplotlib
---

Here's a short snippet of code that describes how to fit a linear curve
for a set of data points using SciPy. Furthermore, its assumed that the
data set is influenced by a single feature.

This code is taken from the wonderful book SciPy and Numpy from Eli
Bressert, with a few changes to actually plot the curve using the
fantastic matplotlib library.

```
import numpy as np
from scipy.optimize import curve_fit
# Creating a function to model and create data
def func(x, a, b):
    return a * x + b
# Generating clean data
x = np.linspace(0, 10, 100)
y = func(x, 1, 2)
# Adding noise to the data
yn = y + 0.9 * np.random.normal(size=len(x))
# Executing curve_fit on noisy data
popt, pcov = curve_fit(func, x, yn)
plot(x,yn,'bo',x,func(x,popt[0],popt[1]))
```