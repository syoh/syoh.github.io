---
title: Interactive Tutorial with learnr and Binder
toc: true
gallery:
- url: https://syoh.org/assets/images/learnr.gif
  image_path: https://syoh.org/assets/images/learnr.gif
  alt: "learnr tutorial on Binder"
  title: "learnr tutorial running on Binder"
tags: [teaching, jupyter, docker, binder, computing]
---

Recently, a colleague pointed out that they would like to host R tutorial created with `learnr` package for their students. In this post, I describe a way to host the tutorials that is suitable in a workshop-like setting.

# Creating Interactive Tutorial with `learnr` Package

[`learnr`](https://rstudio.github.io/learnr/) is a package that creates a specialized Shiny apps for interactive tutorials. The difficulty in making use of `learnr` in practice is that someone needs to host the Shiny apps. Immediate possibilities are

* Host them on [shinyapps.io](https://www.shinyapps.io). The free tier seems to be limited to 5 applications and 25 active hours per month.
* Host them on a central Shiny server the instructor installs. With cloud computing this is possible without a physical machine; however, this option is still time consuming and requires expertise. 
* Student installs Rstudio and runs the tutorials. This can be hard depending on the audience.

First and second options require instructor's resource and time, and third option need students to invest time to setup the environment and run the tutorials themselves.

# "Hosting" Interactive Tutorial with Binder

Binder is a flexible platform to reproduce a computational environment. You can read more about Binder on [The Turing Way](https://the-turing-way.netlify.app/reproducible-research/renv/renv-binder.html) (an online book for research computing that I find super useful).

For example, Binder can start a Rstudio session with cloned contents of a GitHub repository, and start a Shiny app for you.

{% include gallery %}

# Template Code Repository

You can find two interactive tutorial examples in this [`learnr` template Github repository](https://github.com/syoh/learnr-tutorial). You can clone the template repository and start creating your own `learnr` tutorials that will run on Binder!

Below are the two Binder links from the template repository:

* shiny/test1: [![Binder](http://mybinder.org/badge_logo.svg)](http://mybinder.org/v2/gh/syoh/learnr-tutorial/master?urlpath=shiny/test1/)
* shiny/test2: [![Binder](http://mybinder.org/badge_logo.svg)](http://mybinder.org/v2/gh/syoh/learnr-tutorial/master?urlpath=shiny/test2/)
