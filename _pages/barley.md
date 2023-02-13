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

site_variety_avg= df.[[2]].[[3]]
site_maximum = site_variety_avg.[[4]].[[5]]
site_variety_avg.loc[site_maximum.values.flatten()]
```

## Snippet List

i. `groupby('site')`

ii. `agg({'yield':'mean'})`

iii. `groupby(['site', 'variety'])`

iv. `set_index(['site', 'variety'])`

v. `apply(lambda x: x.idxmax())`

