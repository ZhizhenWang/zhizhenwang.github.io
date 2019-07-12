---
layout: post
title:  "Understanding the Micro-Macro Score"
date: 2019-07-12 16:24:55 +0200
tags: ml 
---

When we deal with multiclass or multilabel problems, the data is treated as binary classification problem (either one-vs-one or one-vs-rest). There're several ways to average binary metric values across the set of classes. Which we discussed here is micro and macro method.

`"micro"` gives each sample-class pair an equal contribution to the overall metric (except as a result of sample-weight). Rather than summing the metric per class, this __sums the dividends and divisors__ that make up the per-class metrics to calculate an overall quotient. Micro-averaging may be preferred in __multilabel__ settings, including multiclass classification where a majority class is to be ignored.

`"macro"` simply calculates the mean of the binary metrics, giving equal weight to each class. In problems where infrequent classes are nonetheless important, macro-averaging may be a means of highlighting their performance. On the other hand, the assumption that all classes are equally important is often untrue, such that macro-averaging will __over-emphasize the typically low performance on an infrequent class__.

The abbreviation I used below:  
__TP__: True Positive, __FP__: False Positive, __TN__: True Negative, __FN__: False Negative

The definition of precision, recall are:

$$precision = \frac{TP}{TP+FP}$$

$$recall = \frac{TP}{TP+FN}$$

Assume we have two classes, we use subscript 1, 2 to denote them.


Then the macro precision will be:

$$precision_{macro} = \frac{1}{2}(precision_1+precision_2)=\frac{1}{2} (\frac{TP_1}{TP_1+FP_1} + \frac{TP_2}{TP_2+FP_2})$$

Then the micro precision will be:

$$precision_{micro} =\frac{TP_1+TP_2}{TP_1+FP_1+TP_2+FP_2}$$


If the data set is unbalanced, it's recommended to choose micro score, because macro score gives even weight to each class, and don\'t take the sample size into consideration.

<br/><br/>

Reference:  
- <https://scikit-learn.org/stable/modules/model_evaluation.html#from-binary-to-multiclass-and-multilabel>
- <http://sofasofa.io/forum_main_post.php?postid=1001112>