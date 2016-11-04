---
layout: default
title: Archive
---

### Trend Archive

As data becomes available, we will post it here. PSRC also has an agency-wide [Information Center](http://www.psrc.org/about/infocenter) with data and documents on a wide variety of topics.

All trend articles ever posted, in chronological order:

{% assign years = "2023|2022|2021|2020|2019|2018|2017|2016|2015" | split: "|" %}
{% capture strnowyear %}{{'now' | date: '%Y'}}{% endcapture %}
{% assign nowyear = strnowyear | plus: 0 %}

{% for stryear in years %}
{% assign year = stryear | plus: 0 %}
{% if year <= nowyear %}

{% assign colyear = stryear | plus: 0 %}
{% assign col = 0 %}

<p class="sidebar_title"><h4>{{year}} TRENDS</h4></p>

<table>

{% for post in site.posts %}
{% capture postyear %} {{post.date | date: '%Y'}}{% endcapture %}

{% if postyear contains stryear %}

{% if col == 0 %}<tr>{% endif %}

<td width="33%" valign="top" >
  <div class="archive-thumbnail">
      <a href="{{site.baseurl}}{{post.url}}"><img src="{{site.baseurl}}{{post.image}}" height="100px" width="160px" /></a><br/>
      <div class="archive-tag">
          <a href="{{site.baseurl}}/{{post.tags[0]}}">{{post.tags[0]}}</a> -
          <a class="archive-tag" href="{{site.baseurl}}/trend/{{post.tags[1]}}">{{post.tags[1]}}</a>
      </div>
      <a href="{{site.baseurl}}{{post.url}}">{{ post.title }}</a>
      <br/>
      <i>{{ post.date | date_to_string }}</i>
  </div>
</td>

{% assign col = col | plus: 1 %}

{% if col >2 %}
{% assign col = 0 %}
</tr>
{% endif %}

{% endif %}
{% endfor %}

{% if col == 0 %}<td></td><td></td> {%endif%}
{% if col == 1 %}<td></td> {%endif%}

</tr></table>
{% endif %}
{% endfor %}
