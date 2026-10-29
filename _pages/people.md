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

<nav class="zg-subnav" aria-label="People sections">
  <a href="#pi">PI</a>
  {% for group in site.data.people.groups %}
    <a href="#{{ group.title | slugify }}">{{ group.short | default: group.title }}</a>
  {% endfor %}
</nav>

<section class="zg-people-section" id="pi">
  <h2 class="zg-people-title">Principal investigator</h2>
  <div class="zg-pi-card">
    {% if pi.image and pi.image != '' %}
      <img class="zg-avatar zg-avatar-lg" src="{{ '/assets/img/people/' | append: pi.image | relative_url }}" alt="{{ pi.name }}">
    {% else %}
      {% assign parts = pi.name | split: ' ' %}
      <div class="zg-avatar zg-avatar-lg" aria-hidden="true">{{ parts.first | slice: 0 }}{{ parts.last | slice: 0 }}</div>
    {% endif %}
    <div class="zg-pi-text">
      <h3><a href="{{ pi.url }}">{{ pi.name }}</a></h3>
      <div class="zg-role">{{ pi.role }}</div>
      <p>{{ pi.bio }}</p>
    </div>
  </div>
</section>

{% for group in site.data.people.groups %}
<section class="zg-people-section" id="{{ group.title | slugify }}">
  <h2 class="zg-people-title">{{ group.title }} <span class="zg-count">{{ group.members | size }}</span></h2>
  <div class="zg-people">
    {% for m in group.members %}
      <div class="zg-person">
        {% if m.image and m.image != '' %}
          <img class="zg-avatar" src="{{ '/assets/img/people/' | append: m.image | relative_url }}" alt="{{ m.name }}" loading="lazy">
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
</section>
{% endfor %}

<script>
  /* Highlight the section menu item for the part of the page in view. */
  (function () {
    var links = Array.prototype.slice.call(document.querySelectorAll(".zg-subnav a"));
    var sections = links.map(function (a) {
      return document.querySelector(a.getAttribute("href"));
    });
    function update() {
      var current = 0;
      var offset = window.innerHeight * 0.3;
      sections.forEach(function (s, i) {
        if (s && s.getBoundingClientRect().top <= offset) current = i;
      });
      links.forEach(function (a, i) {
        a.classList.toggle("active", i === current);
      });
      var active = links[current];
      if (active && active.parentNode.scrollWidth > active.parentNode.clientWidth) {
        active.parentNode.scrollLeft = active.offsetLeft - 16;
      }
    }
    window.addEventListener("scroll", update, { passive: true });
    update();
  })();
</script>
