---
layout: archive
title: "Portfolio"
permalink: /portfolio/
excerpt: "Here is a list of neat things that I have made or worked on"
---
Here is a list of neat things that I have made or worked on. Feel free to check them out (hence the reason they are online):

Also, you can check out my resume 
[here]({{ site.baseurl }}/assets/documents/Grant-Garrett-Grossman_resume.pdf){: .btn .btn--info}

***

<div class="grid__wrapper">
  {% for post in site.portfolio %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>