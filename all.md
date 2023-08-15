---
layout: default
title: all
---
{%-
	assign all_files = site.static_files
	| where: "extname", ".apk"
	| sort: "name"
-%}
<ul>
{% for file in all_files %}
<li>
<a href="{{ file.path | relative_url}}">{{ file.name }}</a>
</li> 
{% endfor %}
</ul>
