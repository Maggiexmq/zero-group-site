---
layout: page
permalink: /publications/
title: Publications
description: Selected papers from the group, by topic.
nav: true
nav_order: 1
---

<link rel="stylesheet" href="{{ '/assets/css/zero.css' | relative_url }}">

<!-- Topics: set the `topic` field of an entry in _bibliography/papers.bib to one or more keys
     (space-separated): energy, mobility, game, l2o. To add a topic, copy a block below. -->

<ul class="zg-topics">
  <li><a href="#energy">Power &amp; energy systems</a></li>
  <li><a href="#mobility">Mobility</a></li>
  <li><a href="#game">Game theory &amp; equilibrium seeking</a></li>
  <li><a href="#l2o">Learning to optimize &amp; algorithms</a></li>
</ul>

<div class="publications">

<h2 id="energy">Power &amp; energy systems</h2>
{% bibliography -q @*[topic~=energy] %}

<h2 id="mobility">Mobility</h2>
{% bibliography -q @*[topic~=mobility] %}

<h2 id="game">Game theory &amp; equilibrium seeking</h2>
{% bibliography -q @*[topic~=game] %}

<h2 id="l2o">Learning to optimize &amp; algorithms</h2>
{% bibliography -q @*[topic~=l2o] %}

</div>
