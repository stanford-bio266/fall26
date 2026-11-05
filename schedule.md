---
title: Schedule
nav_order: 2
permalink: /schedule/
---
<!--
  This page builds itself from the class pages (date, title, guest, due, note).
  To change the schedule, edit the settings at the top of the class page instead.
-->

# Schedule

{% assign classes = site.pages | where: "layout", "class" | sort: "nav_order" %}
{% assign parts = classes | group_by: "parent" %}
{% for part in parts %}
<h2>{{ part.name }}</h2>
<table style="table-layout:fixed; width:100%; font-size:0.85em">
<colgroup>
<col style="width:10%">
<col style="width:17%">
<col style="width:38%">
<col style="width:35%">
</colgroup>
<thead>
<tr>
<th style="min-width:0">Class #</th>
<th style="min-width:0">Date</th>
<th style="min-width:0">Topic</th>
<th style="min-width:0">Notes</th>
</tr>
</thead>
<tbody>
{% for c in part.items %}
<tr>
<td style="min-width:0">{{ c.nav_order }}</td>
<td style="min-width:0">{{ c.date }}</td>
<td style="min-width:0"><a href="{{ c.url | relative_url }}">{{ c.title }}</a></td>
<td style="min-width:0">
{% if c.due and c.due != "" %}<span class="label label-red">Due</span> {{ c.due }}<br>{% endif %}
{% if c.guest and c.guest != "" %}<span class="label label-purple">Guest</span> {{ c.guest }}<br>{% endif %}
{% if c.note and c.note != "" %}{{ c.note }}{% endif %}
</td>
</tr>
{% endfor %}
</tbody>
</table>
{% endfor %}
