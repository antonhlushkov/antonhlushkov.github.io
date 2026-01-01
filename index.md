---
title: Home
has_map: true
---
{% include map.html %}

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
    // London center
    var myLat = 51.5074;
    var myLon = -0.1278;
    var zoomLevel = 14;

    var map = L.map('map', {
      zoomControl: false,
      attributionControl: false
    }).setView([myLat, myLon], zoomLevel);

    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      maxZoom: 19,
      attribution: ''
    }).addTo(map);

    // Custom red pin icon (simple and clean)
var redIcon = L.icon({
      iconUrl: 'https://cdn.rawgit.com/pointhi/leaflet-color-markers/master/img/marker-icon-red.png',
      // shadowUrl removed on purpose → no shadow!
      iconSize: [25, 41],     // size of the icon
      iconAnchor: [12, 41],   // point of the icon which will correspond to marker's location
      popupAnchor: [1, -34]   // point from which the popup should open relative to the iconAnchor
    });

    L.marker([myLat, myLon], {icon: redIcon}).addTo(map);
  });
</script>