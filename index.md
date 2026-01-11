---
title: Home
has_map: true
---
{% include map.html %}

**A person who tries to think critically in unpredictable situations. Experienced IT Troubleshooter. IT Systems Manager.**

{% include alert.html
  type="note"
  title="Note"
  text="Available for hire. Based in London, UK." %}

## Link tree

- [Bluesky](https://bsky.app/profile/hlu.bsky.social)
- [X](https://x.com/antonhlushkov)

## Posts

<ul class="posts">
  {% for post in site.posts limit:10 %}
    <li class="posts">
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

  });
</script>