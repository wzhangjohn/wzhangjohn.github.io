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
    Final-Year PhD Student at the London School of Economics and Political Science.
    <br><br>
    Visiting Student Researcher at Stanford University.
  </div>
</div>

Hello, World!

My research addresses topical debates in political economy, technological change and social policy from a historical perspective.

You can find my CV [here](https://wzhangjohn.github.io/files/CV_John_W_Z_Zhang.pdf).

Click [here](https://dx.doi.org/10.2139/ssrn.6372878) for my **Job Market Paper**.

Feel free to reach out at [w.zhang59@lse.ac.uk](mailto:w.zhang59@lse.ac.uk).

{% if site.publication_category %}
{% assign sorted_publications = site.publications | sort: "title" %}
{% assign title_shown = false %}

{% assign sorted_publications = site.publications | sort: "date" | reverse %}
{% for post in sorted_publications %}
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