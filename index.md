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
  // Change these coordinates to your exact location
  var myLat = 37.7749;  // Example: San Francisco latitude
  var myLon = -122.4194; // Example: San Francisco longitude
  var zoomLevel = 14;    // Adjust zoom: 13 = city, 15-16 = neighborhood/street

  var map = L.map('map').setView([myLat, myLon], zoomLevel);

  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors',
    maxZoom: 19,
  }).addTo(map);

  // Add a nice marker with popup
  L.marker([myLat, myLon]).addTo(map)
    .bindPopup('<b>Hello!</b><br>This is my location.')
    .openPopup();
</script>