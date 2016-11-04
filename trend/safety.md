---
layout: default
tags: [safety]
permalink: /trend/safety/
---

### Transportation

<!-- this creates the header links for each trend -->

#### {% for trend in site.data.transportation %}{% if page.tags contains trend %}{{trend}}{% else %}[{{trend}}]({{site.baseurl}}/trend/{{trend}}){% endif %}{% if forloop.last == false %} &bull; {%endif%}{% endfor %}

---
<!-- this grabs the most recent post with the specified tag -->
{% for post in site.posts %}
{% if post.tags contains page.tags[0] %}

<h5 class="author-tight">Updated {{post.date | date: '%b %d %Y'}}, by {{ post.author }}, PSRC</h5>

{{ post.content}}

<!-- break loop to only show very latest post -->
{% break %}
{% endif %}
{% endfor %}
