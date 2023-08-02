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
var parameter = ""; 
parameter = decodeURIComponent(window.location.search.substring(1)).split("&")[0];
function setInput () {
var query = parameter;
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
<b>Попробуйте также поискать здесь:</b><br>
<script>
document.write('<a href="https://play.google.com/store/apps/details?id=' + parameter + '">Google Play</a><br>');
document.write('<a href="https://4pda.to/forum/index.php?act=search&query=' + parameter + '&username=&forums%5B%5D=212&subforums=1&source=pst&sort=rel&result=topics">4PDA</a><br>');
document.write('<a href="https://f-droid.org/packages/' + parameter + '/">F-Droid</a><br>');
document.write('<a href="https://apkcombo.com/ru/' + parameter + '/download/apk">apkcombo (скачать APK)</a><br>');
document.write('<a href="https://apkcombo.com/ru/search/' + parameter + '">apkcombo (поиск)</a><br>');
</script>


<hr>
Протестировать:<br>
<a href="./?q=test">test</a>
<br>

<hr>

<div>
Github Pages | {{ site.theme }}
</div>
</div>




