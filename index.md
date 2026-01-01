---
title: Home
---
<head>
{% if page.has_map %}
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" integrity="sha256-p4NxAoJBhIIN+hmNHrzRCf9tD/miZyoHS5obTRR9BMY=" crossorigin=""/>
  <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js" integrity="sha256-20nQCchB9co0qIjJZRGuk2/Z9VM+kNiyxNV1lvTlZBo=" crossorigin=""></script>
{% endif %}
</head>

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