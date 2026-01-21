---
title: Home
has_map: true
---

London, UK 🇬🇧

{% include map.html %}

A person who tries to think critically in unpredictable situations. Experienced IT Troubleshooter. IT Systems Manager.

<!--
{% include alert.html
  type="note"
  title="Note"
  text="Available for hire. Based in London, UK." %}
-->

## Link tree

- [Bluesky](https://bsky.app/profile/hlu.bsky.social)
- [X](https://x.com/antonhlushkov)

## Posts

<ul class="posts">
  {% for post in site.posts limit:10 %}
<li class="posts">
  <svg class="post-icon" viewBox="0 0 24 24" aria-hidden="true"
       xmlns="http://www.w3.org/2000/svg">
    <g>
      <path d="M20.5,22H4c-0.2,0-0.3,0-0.5,0C1.6,22,0,20.4,0,18.5V6h5V2h19v16.5C24,20.4,22.4,22,20.5,22z M6.7,20h13.8
        c0.8,0,1.5-0.7,1.5-1.5V4H7v14.5C7,19,6.9,19.5,6.7,20z M2,8v10.5C2,19.3,2.7,20,3.5,20S5,19.3,5,18.5V8H2z"/>
      <rect x="15" y="6" width="5" height="6"/>
      <rect x="9" y="6" width="4" height="2"/>
      <rect x="9" y="10" width="4" height="2"/>
      <rect x="9" y="14" width="11" height="2"/>
    </g>
  </svg>

  <strong>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </strong>
  <span style="color: #666;"> — {{ post.date | date: "%B %d, %Y" }}</span>
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