# Notes for me

## Using jekyll-scholar

Creating a publication page from bibtex requires a number of files need to be edited. Here are the essential modifications.

### Installation: `Gemfile`
```
gem "jekyll-scholar"
```

### Configurations: `_config.yml`
```yaml
scholar:
  # style: apa
  style: ./_bibliography/nature.csl
  locale: en

  sort_by: year,month
  order: descending

  bibliography_list_tag: ul

  group_by: none
  group_order: ascending

  source: ./_bibliography
  bibliography: references.bib
  bibliography_template: bib

  replace_strings: true
  join_strings:    true

  details_dir:    bibliography
  details_layout: bibtex.html
  details_link:   Details

  query: "@*"
```

### Citation Style Language (CSL)

I wanted a simple citation style. [Nature citation style](https://paperpile.com/s/nature-citation-style/) seemed close. I modified [`nature.csl`](https://github.com/citation-style-language/styles/blob/master/nature.csl) to

1. Remove DOI tag
2. Unbold journal volume
3. Increase number of listed authors from 6 to 10
4. Remove citation numbering

Following is the `diff`:
```diff
(base) ➜  /tmp diff nature.csl mynature.csl
42d41
<         <text variable="DOI" prefix="doi:"/>
94c93
<         <text variable="volume" font-weight="bold" suffix=","/>
---
>         <text variable="volume" suffix=","/>
112c111
<   <bibliography et-al-min="6" et-al-use-first="1" second-field-align="flush" entry-spacing="0" line-spacing="2">
---
>   <bibliography et-al-min="10" et-al-use-first="1" second-field-align="flush" entry-spacing="0" line-spacing="2">
114d112
<       <text variable="citation-number" suffix="."/>
```
    
### Publications page: `_pages/research.md`

Following resources were useful:
* [General structure of jekyll-scholar](https://gist.github.com/roachhd/ed8da4786ba79dfc4d91)
* [jekyll configuration defaults](https://github.com/inukshuk/jekyll-scholar/blob/master/lib/jekyll/scholar/defaults.rb)

```markdown
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

{% for year in page.years %}
## {{year}}
{% bibliography --query @*[year={{year}}]* %}
{% endfor %}
```

### Layout: `_layouts/bib.html`

Added buttons for DOI/URL and software location.

```html
---
---
{{ reference }}
<div>
	{% if entry.doi %}
    <span><a href="{{ entry.doi | prepend: 'http://doi.org/' }}" class="btn btn--info btn--small">doi</a></span>
	{% elsif entry.url %}
    <span><a href="{{ entry.url }}" class="btn btn--info btn--small">url</a></span>
 	{% endif %}
	{% if entry.software%}
    <span><a href="{{ entry.software }}" class="btn btn--warning btn--small">software</a></span>
 	{% endif %}
</div>
```
