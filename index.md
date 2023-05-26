---
title: Apps
---
<div markdown="0">
<input type="text" id="search-input" placeholder="Введи поисковой запрос.." style="width: 100%; padding: 12px 20px; margin: 8px 0; box-sizing: border-box;">

<ul id="results-container"></ul>

<script src="{{ site.baseurl }}/simple-jekyll-search.js"></script>

<script>
  window.simpleJekyllSearch = new SimpleJekyllSearch({
	searchInput: document.getElementById('search-input'),
	resultsContainer: document.getElementById('results-container'),
	json: '{{ site.baseurl }}/apps.json',
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

<br>
<hr>
<br>


</div>




