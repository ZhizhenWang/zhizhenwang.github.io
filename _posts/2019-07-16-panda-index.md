---
layout: post
title:  "iloc and loc"
date: 2019-07-12 16:24:55 +0200
tags: pandas
published: true
categories: Tech
---

iloc 截取真实第几行的dataframe
loc  截取dataframe中index为符合需要的dataframe
```
df = pd.DataFrame({'BoolCol': [True, False, False, True, True]},
       index=[10,20,30,40,50])

In [53]: df
Out[53]: 
   BoolCol
10    True
20   False
30   False
40    True
50    True

df.iloc[[0, 3, 4]]
df.loc[[10, 40, 50]]
```