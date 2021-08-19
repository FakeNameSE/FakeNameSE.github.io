---
layout: archive
title: "Portfolio"
permalink: /portfolio/
excerpt: "Here is a list of neat things that I have made or worked on"
---
Here is a list of some neat things that I have made or worked on. Feel free to check them out (hence the reason they are online):

My resume is available upon request. If interested, please email [me](mailto:grant.garrettgrossman@gmail.com).

***

<div class="grid__wrapper">
  {% for post in site.portfolio %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>