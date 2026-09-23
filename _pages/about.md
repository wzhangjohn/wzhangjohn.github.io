---
permalink: /
title: "Hello, World!"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am a final-year PhD student in the Department of Economic History at the London School of Economics and Political Science (LSE).

I am visiting the Department of Political Science at Stanford University in Autumn 2026.

My research addresses topical debates in political economy, technological change and social policy, from a historical perspective.

You can find my CV [here](https://wzhangjohn.github.io/files/CV_John_W_Z_Zhang.pdf).

**Click [here](https://dx.doi.org/10.2139/ssrn.6372878) for my Job Market Paper.**

Feel free to reach out at: [w.zhang59@lse.ac.uk](mailto:w.zhang59@lse.ac.uk).

<h1>Research</h1>

Next Release: <strong>Austerity Origins of the Great Reform Act</strong>

{% if site.publication_category %}
{% for category in site.publication_category %}
{% assign title_shown = false %}

{% for post in site.publications reversed %}
{% if post.category != category[0] %}
{% continue %}
{% endif %}

{% unless title_shown %}
<h2>{{ category[1].title }}</h2>
<hr>
{% assign title_shown = true %}
{% endunless %}

<h3><a href="{% if post.paperurl %}{{ post.paperurl }}{% else %}{{ post.url | relative_url }}{% endif %}">{{ post.title }}</a></h3>

{% if post.coauthor %}
<p class="publication-coauthor">{{ post.coauthor }}</p>
{% endif %}

{% if post.excerpt %}
<details class="research-excerpt">
<summary>Abstract</summary>
<div class="excerpt-content">
{{ post.excerpt }}
</div>
</details>
{% endif %}

{% endfor %}
{% endfor %}
{% endif %}