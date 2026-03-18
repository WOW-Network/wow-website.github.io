---
layout: archive
permalink: /posts/
entries_layout: list   # or 'grid' for grid layout
---

{% assign postsByYear = site.posts | where_exp: "item", "item.hidden != true" | group_by_exp: 'post', 'post.date | date: "%Y"' %}
{% for year in postsByYear %}
  <div class="entries-{{ page.entries_layout }}">
    {% for post in year.items %}
      {% include archive-single.html type=page.entries_layout %}
    {% endfor %}
  </div>
{% endfor %}