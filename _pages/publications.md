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
<b>[{{ p.title }}]{% if p.links and p.links.paper %}({{ p.links.paper }}){% endif %}</b> <br>
{{ p.authors }}<br>
<i class="publication-conference">{{ p.venue }}</i>
<br>
{% if p.links.paper %}[[📝 paper]]({{ p.links.paper }}) {% endif %}
{% if p.links.video %} [[🎥 video]]({{ p.links.video }}){% endif %}
{% if p.links.code %} [[💻 code]]({{ p.links.code }}){% endif %}
{% if p.links.poster %} [[🖼️ Poster]]({{ p.links.poster }}){% endif %}

<br>
{% endfor %}

{% endfor %}

