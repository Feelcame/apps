---
title: Apps
---
<div markdown="0">
<input type="text" id="search-input" placeholder="Введи поисковой запрос.." style="width: 100%; padding: 12px 20px; margin: 8px 0; box-sizing: border-box;">

<ul id="results-container"></ul>

<script src="{{ 'simple-jekyll-search.js' | relative_url }}"></script>

<script>
  window.simpleJekyllSearch = new SimpleJekyllSearch({
	searchInput: document.getElementById('search-input'),
	resultsContainer: document.getElementById('results-container'),
	json: '{{ "apps.json" | relative_url }}',
	searchResultTemplate: '<li><a href="{url}" target="_blank">{name}</a></li>',
	noResultsText: 'No results found',
	limit: 20,
	fuzzy: false,
	exclude: ['Welcome']
  })
</script>


<script>
function setInput () {
var query = decodeURIComponent(window.location.search.substring(1)).split("&")[0];
var key = query.split("=")[0];
var val = query.split("=")[1];
var field = document.getElementById('search-input');
	if (key == "q" && val.length > 0) {
		field.value = val;
		const event = new Event('input');
		field.dispatchEvent(event);
	} else {
		document.querySelector('#search-input').focus();
	}
return false;
}
setTimeout(setInput, 500);
</script>


<hr>
<a href="./?q=test">test</a>
<br>

<div>
{{ site.theme }}
</div>
</div>


---

- "site.baseurl": `{{ site.baseurl }}`
- "pages_hostname": `{{ site.github.pages_hostname }}`
- "owner_name": `{{ site.github.owner_name }}`
- "repository_name": `{{ site.github.metadata-example }}`
- "url" (or the CNAME): `{{ site.github.url }}`



