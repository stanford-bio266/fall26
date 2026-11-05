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
<table>
<thead>
<tr>
<th style="min-width:5.5rem; width:5.5rem; white-space:nowrap">Class #</th>
<th style="min-width:8.5rem; width:8.5rem; white-space:nowrap">Date</th>
<th style="min-width:15rem">Topic</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
{% for c in part.items %}
<tr>
<td style="min-width:5.5rem; width:5.5rem">{{ c.nav_order }}</td>
<td style="min-width:8.5rem; width:8.5rem; white-space:nowrap">{{ c.date }}</td>
<td style="min-width:15rem"><a href="{{ c.url | relative_url }}">{{ c.title }}</a></td>
<td style="font-size:0.9em">
{% if c.due and c.due != "" %}<span style="white-space:nowrap"><span class="label label-red">Due</span> {{ c.due }}</span><br>{% endif %}
{% if c.guest and c.guest != "" %}<span style="white-space:nowrap"><span class="label label-purple">Guest</span> {{ c.guest }}</span><br>{% endif %}
{% if c.note and c.note != "" %}{{ c.note }}{% endif %}
</td>
</tr>
{% endfor %}
</tbody>
</table>
{% endfor %}
