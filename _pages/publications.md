---
layout: page
permalink: /publications/
title: Publications
description: Selected papers from the group.
nav: true
nav_order: 1
---

<link rel="stylesheet" href="{{ '/assets/css/zero.css' | relative_url }}">

<!-- Sections: set the `topic` field of an entry in _bibliography/papers.bib
     (theory, energy, mobility, social). Entries without a topic are not listed. -->

<ul class="zg-topics">
  <li><a href="#theory">Theory: games, optimization &amp; learning</a></li>
  <li><a href="#energy">Application: power &amp; energy systems</a></li>
  <li><a href="#mobility">Application: mobility</a></li>
  <li><a href="#social">Application: social networks</a></li>
</ul>

<div class="publications">

<h2 id="theory">Theory: games, optimization &amp; learning</h2>
{% bibliography -q @*[topic=theory] %}

<h2 id="energy">Application: power &amp; energy systems</h2>
{% bibliography -q @*[topic=energy] %}

<h2 id="mobility">Application: mobility</h2>
{% bibliography -q @*[topic=mobility] %}

<h2 id="social">Application: social networks</h2>
{% bibliography -q @*[topic=social] %}

</div>
