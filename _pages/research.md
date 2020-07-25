---
permalink: /research/
title: "Publications"
layout: single
header:
    image: /assets/images/fgm-lr-task.png
author_profile: true
toc: true
years: [2020,2019,2018,2017,2016,2014,2012,2011,2001,2000]
---

<!--
helpful writeup on jekyll-scholar
https://gist.github.com/roachhd/ed8da4786ba79dfc4d91

jekyll defaults
https://github.com/inukshuk/jekyll-scholar/blob/master/lib/jekyll/scholar/defaults.rb
-->

{% for year in page.years %}
## {{year}}
{% bibliography --query @*[year={{year}}]* %}
{% endfor %}

