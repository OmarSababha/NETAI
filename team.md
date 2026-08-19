---
layout: default
title: Team
nav_order: 2
---
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-E09K8XMPK5"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-E09K8XMPK5');
</script>

# Our Team

{%- assign lead = site.data.team | where: "group", "lead" | first %}

## Team Lead

<img src="{{ lead.photo | relative_url }}" alt="{{ lead.name }}" style="width: 150px;">

**{{ lead.name }}**, {{ lead.role }}

{{ lead.bio | markdownify }}

### Connect
{% for l in lead.links %}
- [{{ l.label }}]({{ l.url }}){% endfor %}

{% for g in site.data.team_groups %}{% unless g.id == "lead" %}
## {{ g.heading }}

{% include people_list.html group=g.id show_projects=true empty="To be announced." %}
{% endunless %}{% endfor %}
