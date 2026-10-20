---
layout: page
title: Writing
---

<div class="posts">
	{% for post in site.posts %}
	<a class="post post-link" href="{{ post.url }}">
		<img class="post-img"
			src="{{ post.image | default: 'data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTI1IiBoZWlnaHQ9IjEyNSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMTI1IiBoZWlnaHQ9IjEyNSIgZmlsbD0iI2ZmMDAwMCIvPjwvc3ZnPg==' }}"
			alt="{{ post.title }}" />
		<h3>{{ post.title }}</h3>
		<p>{{ post.quote }}</p>
	</a>
	{% endfor %}
</div>
