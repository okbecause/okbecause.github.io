<div class="posts">

{% for post in site.posts limit: 5 %}

<div class="gloop" style="display: table;">

<a style="display: table-row;" href="{{ site.baseurl }}{{ post.url }}">

	<div style="display:table-cell; vertical-align: top;">
	    <img class="entry_image" src="{{ site.baseurl }}{{ post.image }}" alt="{{ post.title }}" />
	</div>

	<div style="display: table-cell; vertical-align: top; color:#4d4d4d">
		<h5 class="index_entry"><font size="-2" color="#bbb">{{ post.date | date: '%B %Y' }}</font><br/>
    	<div class="entry_list_link" href="{{ site.baseurl }}{{ post.url }}"><font style="color:#4545c0;">{{ post.title }}</font></div>
    	</h5>

    	{{ post.excerpt }} <font style="color:#f80">&nbsp;&nbsp;&nbsp;&raquo;&nbsp;Read&nbsp;more</font>
    </div>
</a>

</div>

{% if forloop.last == false %}
  <div class="faint_border"></div>
{% endif %}

{% endfor %}

</div>
