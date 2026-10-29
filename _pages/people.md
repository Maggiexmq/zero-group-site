---
layout: page
title: People
permalink: /people/
description: Everyone is either formally co-advised or integrated through various collaborations.
nav: true
nav_order: 2
---

<link rel="stylesheet" href="{{ '/assets/css/zero.css' | relative_url }}">

<!-- This page is generated from _data/people.yml. Edit that file to add, remove or reorder people. -->

{% assign pi = site.data.people.pi %}
<div class="zg-group">Principal investigator</div>
<div class="zg-pi">
  {% if pi.image and pi.image != '' %}
    <img class="zg-avatar" src="{{ '/assets/img/people/' | append: pi.image | relative_url }}" alt="{{ pi.name }}">
  {% else %}
    {% assign parts = pi.name | split: ' ' %}
    <div class="zg-avatar" aria-hidden="true">{{ parts.first | slice: 0 }}{{ parts.last | slice: 0 }}</div>
  {% endif %}
  <div>
    <h3 style="margin: 0"><a href="{{ pi.url }}">{{ pi.name }}</a></h3>
    <div class="zg-facts">{{ pi.role }}</div>
    <p style="margin-top: 0.6rem">{{ pi.bio }}</p>
  </div>
</div>

{% for group in site.data.people.groups %}
  <div class="zg-group">{{ group.title }}</div>
  <div class="zg-people">
    {% for m in group.members %}
      <div class="zg-person">
        {% if m.image and m.image != '' %}
          <img class="zg-avatar" src="{{ '/assets/img/people/' | append: m.image | relative_url }}" alt="{{ m.name }}">
        {% else %}
          {% assign parts = m.name | split: ' ' %}
          <div class="zg-avatar" aria-hidden="true">{{ parts.first | slice: 0 }}{{ parts.last | slice: 0 }}</div>
        {% endif %}
        <div class="zg-name">
          {% if m.url and m.url != '' %}<a href="{{ m.url }}">{{ m.name }}</a>{% else %}{{ m.name }}{% endif %}
        </div>
        {% if m.note and m.note != '' %}<div class="zg-note">{{ m.note }}</div>{% endif %}
        {% if m.bio and m.bio != '' %}<p class="zg-bio">{{ m.bio }}</p>{% endif %}
      </div>
    {% endfor %}
  </div>
{% endfor %}
