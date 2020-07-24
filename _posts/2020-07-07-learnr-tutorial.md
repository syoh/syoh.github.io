---
title: Interactive Tutorial with `learnr` and Binder
toc: true
---

# Creating Interactive Tutorial with `learnr` Package

[`learnr` Package](https://rstudio.github.io/learnr/) is a package that creates a specialized Shiny apps for interactive tutorials. While useful, the difficult part for students is often installing the software and running them to go through the tutorials, and, for the teachers, it would be great *not* to have to maintain a Shiny server.

# "Hosting" Interactive Tutorial with Binder

Binder is a flexible platform to reproduce a computational environment. You can read more about Binder [here](https://the-turing-way.netlify.app/reproducible-research/renv/renv-binder.html)

For example, Binder can start a Rstudio session with cloned contents of a GitHub repository, and start a Shiny app for you.

# An Example Tutorial on Binder

I created two interactive tutorial examples in this [Github](https://github.com/syoh/learnr-tutorial). Below are the two Binder links you can try out

* shiny/test1: [![Binder](http://mybinder.org/badge_logo.svg)](http://mybinder.org/v2/gh/syoh/learnr-tutorial/master?urlpath=shiny/test1/)
* shiny/test2: [![Binder](http://mybinder.org/badge_logo.svg)](http://mybinder.org/v2/gh/syoh/learnr-tutorial/master?urlpath=shiny/test2/)
