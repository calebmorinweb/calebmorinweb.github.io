---
layout: page
title: "Posts"
permalink: /posts/
main_nav: true
pagination: 
  enabled: true
---

<div class="wrapper">
<ul class="post-list">
  {% for post in site.posts %}
  <li>
    <h2>
      <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
    </h2>
    <section class="post-excerpt" itemprop="description">
      <p>{{ post.content | strip_html | truncatewords: 50 }}</p>
    </section>
    <section class="post-meta">
      <div class="post-date">{{ post.date | date: "%B %-d, %Y" }}</div>
      <div class="post-categories">
      {% if post.categories.size > 0 %}in {% for cat in post.categories %}
        {% if site.jekyll-archives %}
        <a href="{{ site.baseurl }}/category/{{ cat }}">{{ cat | capitalize }}</a>{% if forloop.last == false %}, {% endif %}
        {% else %}
        <a href="{{ site.baseurl }}/posts/#{{ cat }}">{{ cat | capitalize }}</a>{% if forloop.last == false %}, {% endif %}
        {% endif %}
      {% endfor %}{% endif %}
      </div>
    </section>
  </li>
  {% if forloop.last == false %}
  <hr>
  {% endif %}
  {% endfor %}
</ul>

</div>
