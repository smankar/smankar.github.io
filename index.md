---
layout: page
comments: true
permalink: /
---

<div class="blog-index">
  {% assign post = site.posts.first %}
  {% assign content = post.content %}
  {% include post_detail.html %}
</div>

