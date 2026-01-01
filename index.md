---
title: Home
has_map: true
---
{% include map.html %}
📍London, UK


**A person who tries to think critically in unpredictable situations. Experienced IT Troubleshooter. IT Systems Manager.**



{% include alert.html
  type="note"
  title="Note"
  text="Available for hire." %}

## Projects

Coming soon.

## Posts

<ul>
  {% for post in site.posts limit:10 %}
    <li>
      <strong><a href="{{ post.url | relative_url }}">{{ post.title }}</a></strong> 
      <span style="color: #666;">— {{ post.date | date: "%B %d, %Y" }}</span>
    </li>
  {% endfor %}
</ul>

{% if site.posts.size > 10 %}
  <p><a href="/posts/">View all posts →</a></p>
{% endif %}

<footer>
    <p>© 2026 Anton Hlushkov</p>
  <p>This page is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nd/4.0/">Creative
Commons Attribution-NoDerivatives 4.0 International License</a></p>
</footer>

<script>
  

	const map = L.map('map').setView([51.505, -0.09], 13);

	const tiles = L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
		maxZoom: 19,
		attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>'
	}).addTo(map);

	const marker = L.marker([51.5, -0.09]).addTo(map)
		.bindPopup('<b>Hello world!</b><br />I am a popup.').openPopup();

	const circle = L.circle([51.508, -0.11], {
		color: 'red',
		fillColor: '#f03',
		fillOpacity: 0.5,
		radius: 500
	}).addTo(map).bindPopup('I am a circle.');

	const polygon = L.polygon([
		[51.509, -0.08],
		[51.503, -0.06],
		[51.51, -0.047]
	]).addTo(map).bindPopup('I am a polygon.');


	const popup = L.popup()
		.setLatLng([51.513, -0.09])
		.setContent('I am a standalone popup.')
		.openOn(map);

	function onMapClick(e) {
		popup
			.setLatLng(e.latlng)
			.setContent(`You clicked the map at ${e.latlng.toString()}`)
			.openOn(map);
	}

	map.on('click', onMapClick);
</script>