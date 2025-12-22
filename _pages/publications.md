---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% include base_path %}

{% assign pubs_by_year = site.data.publications | sort: 'year' | reverse %}

{% for year_block in pubs_by_year %}
<h2>{{ year_block.year }}</h2>
<hr>

{% for p in year_block.items %}
<b>{% if p.links and p.links.paper %}[{{ p.title }}]({{ p.links.paper }}){% else %}{{ p.title }}{% endif %}</b><br>
{{ p.authors }}<br>
<i class="publication-conference">{{ p.venue }}</i>
<br>
{% if p.links and p.links.paper %}[[📝 Paper]]({{ p.links.paper }}) {% endif %}
{% if p.links and p.links.poster %}[[🖼️ Poster]]({{ p.links.poster }}) {% endif %}
<br>
{% endfor %}

{% endfor %}