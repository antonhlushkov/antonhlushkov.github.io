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
  document.addEventListener('DOMContentLoaded', function() {
    // London center coordinates
    var myLat = 51.5074;
    var myLon = -0.1278;
    var zoomLevel = 14;

    // Clean map without attribution or controls
    var map = L.map('map', {
      zoomControl: false,  // No zoom buttons
      attributionControl: false  // No attribution
    }).setView([myLat, myLon], zoomLevel);

    // Tiles WITHOUT attribution text
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      maxZoom: 19,
      attribution: ''  // Empty attribution
    }).addTo(map);

    // Only a simple marker, no popup
    L.marker([myLat, myLon]).addTo(map);
  });
</script>