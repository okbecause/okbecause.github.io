{% for post in site.posts %}
{% if post.tags contains trend %} <!-- grabs posts for this trend in chrono order -->

<div class="gloop" style="display: table;">

<a style="display: table-row;" href="{{ site.baseurl }}/trend/{{trend}}">

	<div style="display:table-cell; vertical-align: top;">
	    <img class="entry_image" src="{{ site.baseurl }}{{ post.image }}" alt="{{ post.title }}" />
	</div>

	<div style="display: table-cell; vertical-align: top; color:#4d4d4d">
		<h4><div class="entry_list_link" href="{{ site.baseurl }}{{ post.url }}"><font style="color:#4545c0;">{{trend}}</font></div></h4>

		<b>{{ post.title }}.</b> {{ post.excerpt}}<font style="color:#f80">&nbsp;&nbsp;&nbsp;&raquo;&nbsp;Read&nbsp;more</font>
    </div>
</a>

</div>


{%break%}  <!-- break the loop: we only want the most recent post for this trend -->

{% endif %}

{% endfor %}
