---
layout: single
permalink: /barley/
title: Barley
author_profile: true
toc: false
---

## Starter Code

```python
import pandas as pd

df = pd.read_csv("https://syoh.org/assets/files/barley.csv").[[1]]

variety_totals = df.[[2]].[[3]]
variety_minimum = variety_totals.[[4]].[[5]]
variety_totals.loc[variety_minimum.values.flatten()]
```

## Snippet List

i. `groupby('variety')`  

ii. `apply(lambda x: x.idxmin())`  

iii. `set_index(['site', 'variety'])`  

iv. `agg({'yield':'sum'})`  

v. `groupby(['site', 'variety'])`  
