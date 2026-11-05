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
<div class="table-wrapper"><table>
<thead><tr><th>#</th><th>Date</th><th>Topic</th><th>Notes</th></tr></thead>
<tbody>
{% for c in part.items %}
<tr>
<td>{{ c.nav_order }}</td>
<td style="white-space:nowrap">{{ c.date }}</td>
<td><a href="{{ c.url | relative_url }}">{{ c.title }}</a></td>
<td>
{% if c.due and c.due != "" %}<span class="label label-red">Due</span> {{ c.due }}<br>{% endif %}
{% if c.guest and c.guest != "" %}<span class="label label-purple">Guest</span> {{ c.guest }}<br>{% endif %}
{% if c.note and c.note != "" %}{{ c.note }}{% endif %}
</td>
</tr>
{% endfor %}
</tbody></table></div>
{% endfor %}
