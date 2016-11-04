---
layout: default
title: People and Place
tags: [peopleandplace]
---

### Growth: People and Place

Our region is growing. A nice region doesn't just happen by accident: planning for growth is essential for maintaining the quality of life that makes our Northwest so desirable.

Read on for the latest trends in our regional people and places.

{% for trend in site.data.peopleandplace %}

---
{% include section_summary.md %}

{% endfor %}
