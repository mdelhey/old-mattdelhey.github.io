---
layout: draft
title: 'More Titanic: Implimenting TBaker's model'
date:  2013-11-01

---
[TBarker](http://kaggle.com/users/9347/tbarker) wrote a [blog post](http://tfbarker.wordpress.com/2013/12/22/datamining/) on getting past 20% missclassification error by:

1. Feature selection/data preprocessing: using the title of names as a feature. It's interesting that so much predictive power was found here, as I had originally tried the same idea without much success, perhaps due to a coding error. A similar idea was used for creating features from the ticket numbers (e.g. "P2938" --> "P"). 

2. Esnembling randomforests, gradient boosting, and SVM's through a simple majority vote. I had done the same, instead using logistic regression instead of gradient boosting.

I was never far off from Mr. TBarker, but I never did break the 0.8 barrier and so let's impliment his model in R.

