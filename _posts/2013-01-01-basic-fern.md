---
layout: post
title: 'Basic Python: Creating a Fern'
date:   2013-01-01
excerpt: In this short post I'm going to demonstrate how to use __Scipy__ and __matplotlib__ to make a basic graph of a fern. This is inspired from an introductory computational mathematics course that I'm currently taking in which we did the same task using __MATLAB__. Personally, I find __MATLAB__ to be less satisfying than __Python__, so I thought it pleasant to make a quick translation. 

---

In this short post I'm going to demonstrate how to use __Scipy__ and __matplotlib__ to make a basic graph of a fern. This is inspired from an introductory computational mathematics course that I'm currently taking in which we did the same task using __MATLAB__. Personally, I find __MATLAB__ to be less satisfying than __Python__, so I thought it pleasant to make a quick translation. 

The basic idea is to plot a few thousand points by generated by a few basic transformations. Each transformation is created using a given probability. Pretty basic, but an interesting exercise none-the-less. One nice thing about using __Numpy__ is that it has built-in __MATLAB__ matrix notation using _mat_ rather than forcing us to use the default _array_. As always, code can be found at the end of the post. 

### Python Fern
![python fern]({{ site.url }}/images/python_small.png)

{% highlight python %}
from scipy import *
import matplotlib.pyplot as plt

z = mat("0; 0")
for j in xrange(1, 8000):
    r = random.random()
    if r < 0.01:
        z = mat("0 0; 0 0.16")*z
    elif 0.01 <= r and r < 0.86:
        z = mat("0.85 0.04; -0.04 0.85")*z + mat("0; 1.6")
    elif 0.86 <= r and r < 0.93:
        z = mat("0.2 -0.26; 0.23 0.22")*z + mat("0; 1.6")
    else:
        z = mat("-0.15 0.28; 0.26 0.24")*z + mat("0; 0.44")
    plt.plot(z[0], z[1], 'r.', markersize=1)
    plt.hold(True) 
plt.axis('off')
plt.show()
{% endhighlight %}
