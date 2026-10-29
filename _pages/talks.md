---
layout: page
title: Talks & Meetings
permalink: /talks/
description: Regular seminars and meetings, hosted talks, and workshops.
nav: true
nav_order: 4
---

<link rel="stylesheet" href="{{ '/assets/css/zero.css' | relative_url }}">

## Regular series

<div class="zg-card zg-section" style="margin-top: 1rem">
  <h3>Game on! seminar series <span class="zg-status">Season 2 · Jan 2027</span></h3>
  <p>A seminar series on game theory, control, and intelligent systems. Talks are streamed live on Zoom and recorded to YouTube. Season 1 has concluded with 20 talks; the series returns in January 2027.</p>
  <div class="zg-facts">Online · Zoom · Recordings on YouTube · Contact: Emilio Benenati</div>
  <div class="zg-tags">
    <a href="https://gameonseminars.info/">All talks and mailing list</a>
    <a href="https://www.youtube.com/@gameonseminars">YouTube</a>
  </div>
</div>

<div class="zg-card" style="margin-top: 1rem">
  <h3>Group meeting <span class="zg-status zg-tbd">Details to be added</span></h3>
  <p>Regular internal meeting of the group. Schedule, room and format to be added.</p>
</div>

## Hosted talks

<!-- Generated from _data/talks.yml (section "hosted"). -->
{% if site.data.talks.hosted and site.data.talks.hosted.size > 0 %}
<div class="table-responsive">
<table class="zg-table">
  <thead><tr><th>Date</th><th>Speaker</th><th>Talk</th></tr></thead>
  <tbody>
  {% for t in site.data.talks.hosted %}
    <tr>
      <td style="white-space: nowrap">{{ t.date | date: '%b %d, %Y' }}</td>
      <td>{{ t.speaker }}{% if t.affiliation %}<br><span class="zg-facts">{{ t.affiliation }}</span>{% endif %}</td>
      <td>{% if t.url %}<a href="{{ t.url }}">{{ t.title }}</a>{% else %}{{ t.title }}{% endif %}{% if t.place %}<br><span class="zg-facts">{{ t.place }}</span>{% endif %}</td>
    </tr>
  {% endfor %}
  </tbody>
</table>
</div>
{% else %}
<div class="zg-empty">No hosted talks listed yet.</div>
{% endif %}

## Workshops we organize

<!-- Generated from _data/talks.yml (section "workshops"). -->
<table class="zg-table">
  <tbody>
  {% for w in site.data.talks.workshops %}
    <tr>
      <td style="white-space: nowrap; width: 7rem">{{ w.date }}</td>
      <td>{% if w.url %}<a href="{{ w.url }}"><strong>{{ w.title }}</strong></a>{% else %}<strong>{{ w.title }}</strong>{% endif %}<br><span class="zg-facts">{{ w.venue }}</span></td>
    </tr>
  {% endfor %}
  </tbody>
</table>
