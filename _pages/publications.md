---
layout: page
permalink: /research/
title: Research
hide_title: true
description: 
nav: true
nav_order: 2
---
<!-- _pages/publications.md -->
<div class="publications">

{%- assign section_rendered = false -%}

{% capture pub_count %}{% bibliography_count -f {{ site.scholar.bibliography }} --query @*[status=pub]* %}{% endcapture %}
{%- assign pub_count = pub_count | strip | plus: 0 -%}
{%- if pub_count > 0 -%}
{%- if section_rendered -%}<hr>{%- endif -%}
<h2 class="bibliography-section-title">Publications</h2>
{% bibliography -f {{ site.scholar.bibliography }} --group_by none --query @*[status=pub]* %}
{%- assign section_rendered = true -%}
{%- endif -%}

{% capture working_count %}{% bibliography_count -f {{ site.scholar.bibliography }} --query @*[status=working]* %}{% endcapture %}
{%- assign working_count = working_count | strip | plus: 0 -%}
{%- if working_count > 0 -%}
{%- if section_rendered -%}<hr>{%- endif -%}
<h2 class="bibliography-section-title">Working Papers</h2>
{% bibliography -f {{ site.scholar.bibliography }} --group_by none --query @*[status=working]* %}
{%- assign section_rendered = true -%}
{%- endif -%}

{% capture wip_count %}{% bibliography_count -f {{ site.scholar.bibliography }} --query @*[status=wip]* %}{% endcapture %}
{%- assign wip_count = wip_count | strip | plus: 0 -%}
{%- if wip_count > 0 -%}
{%- if section_rendered -%}<hr>{%- endif -%}
<h2 class="bibliography-section-title">Selected Work in Progress</h2>
{% bibliography -f {{ site.scholar.bibliography }} --group_by none --query @*[status=wip]* %}
{%- assign section_rendered = true -%}
{%- endif -%}

</div>
