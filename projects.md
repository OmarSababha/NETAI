---
layout: default
title: Projects
nav_order: 3
has_children: true
---
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-E09K8XMPK5"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-E09K8XMPK5');
</script>

# Current Projects

Four lines of work run in the group. Each one below opens onto its own page, with a
fuller description, the people working on it, and the publications it has produced.

<div class="project-grid">
{%- for p in site.data.projects -%}
{%- assign pub_count = 0 -%}
{%- for pub in site.data.publications -%}
  {%- if pub.projects contains p.id -%}{%- assign pub_count = pub_count | plus: 1 -%}{%- endif -%}
{%- endfor -%}
{%- assign people_count = 0 -%}
{%- for m in site.data.team -%}
  {%- unless m.group == "past" -%}
    {%- if m.projects contains p.id -%}{%- assign people_count = people_count | plus: 1 -%}{%- endif -%}
  {%- endunless -%}
{%- endfor -%}
<a class="project-card" href="{{ p.url | relative_url }}">
{%- if p.image %}<span class="project-thumb" style="background-image:url('{{ p.image | relative_url }}')"></span>{% endif %}
<span class="project-card-body">
<span class="project-card-title">{{ p.title }}</span>
<span class="project-card-blurb">{{ p.blurb }}</span>
<span class="project-card-meta">{{ people_count }} {% if people_count == 1 %}member{% else %}members{% endif %} &middot; {{ pub_count }} {% if pub_count == 1 %}publication{% else %}publications{% endif %}</span>
</span>
</a>
{%- endfor -%}
</div>

Earlier work — including the PhD research on NFV-enabled multicast services, wireless
fading channel analysis, and spectrum sensing for cognitive radio — is collected on the
[past research](research.html) page.
