---
permalink: /
author_profile: false
classes: homepage
redirect_from: 
  - /about/
  - /about.html
---
<div class="homepage-profile">
  <img src="/images/PHOTO.jpg" alt="John W. Z. Zhang">

  <div class="homepage-bio">
    Final-Year PhD Candidate at the London School of Economics and Political Science.
    <br><br>
    Visiting Student Researcher at Stanford University.
  </div>
</div>

Hello, World!

My research addresses topical debates in political economy, technological change and social policy from a historical perspective.

You can find my CV [here](https://wzhangjohn.github.io/files/CV_John_W_Z_Zhang.pdf).

**Click [here](https://dx.doi.org/10.2139/ssrn.6372878) for my Job Market Paper.**

Feel free to reach out at [w.zhang59@lse.ac.uk](mailto:w.zhang59@lse.ac.uk).

<hr style="margin-top: 2.5em; margin-bottom: 1.5em;">

{% if site.publication_category %}
{% for category in site.publication_category %}
{% assign title_shown = false %}

{% for post in site.publications reversed %}
{% if post.category != category[0] %}
{% continue %}
{% endif %}

{% unless title_shown %}
<h2>{{ category[1].title }}</h2>
{% assign title_shown = true %}
{% endunless %}

{% if post.paperurl %}
<h3><a href="{{ post.paperurl }}">{{ post.title }}</a></h3>
{% else %}
<h3>{{ post.title }}</h3>
{% endif %}

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