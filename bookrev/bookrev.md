---
layout: post
title: Book Reviews
---

{% for post in site.categories.bookrev  limit:4 %}
  <h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
  <p class="author">
    <span class="date">{{ post.date | date: "%-d %B %Y"  }}</span>
  </p>
  <div class="content">
    {{ post.content }}
  </div>
{% endfor %}

---

# Previous posts

{% assign postsByYear =
    site.categories.scatolone | group_by_exp:"post", "post.date | date: '%Y'" %}
<ul>
{% for year in postsByYear %}
<li>{{ year.name }}
    <ul>
      {% for post in year.items %}
        <li><a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%-d %B %Y"  }}</li>
      {% endfor %}
    </ul>
 </li>
{% endfor %}
 </ul>
