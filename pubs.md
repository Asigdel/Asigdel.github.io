---
title: Publications
layout: page
---

# My Publications

{% assign pubs = site.static_files | where: "extname", ".md" | where_exp: "file", "file.path contains '_publications/'" | sort | reverse %}

{% for pub in pubs %}
  {% assign pub_path = pub.path | remove_first: "_" %}
  {% assign pub_content = site.pages | where: "path", pub_path | first %}
  
  {% if pub_content %}
    <div class="publication">
      {{ pub_content.content | markdownify }}
    </div>
    <hr>
  {% endif %}
{% endfor %}
