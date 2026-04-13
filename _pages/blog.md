---
layout: archive
permalink: /blog/
title: "Blog"
author_profile: true
---

{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% if year != written_year %}
    <h2 id="{{ year }}-ref">{{ year }}</h2>
    {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}
  <span>[<a href="{{ post.url }}">{{ post.title }}</a>] - {{ post.date | date: "%B %d, %Y" }}</span><br />
{% endfor %}
