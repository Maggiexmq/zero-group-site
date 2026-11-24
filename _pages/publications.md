---
layout: page
permalink: /publications/
title: Publications
description: Selected papers from the group, by research topic.
nav: true
nav_order: 1
---

<link rel="stylesheet" href="{{ '/assets/css/zero.css' | relative_url }}">

<!-- Topics follow the research areas in Giuseppe's postdoc call.
     To move a paper, change its `topic` field in _bibliography/papers.bib
     (game / hier / ofo / mpc / arch). To add a topic, copy a block below and use a new key. -->

<ul class="zg-topics">
  <li><a href="#game">Game-theoretic control</a></li>
  <li><a href="#hier">Hierarchical game theory for incentive design</a></li>
  <li><a href="#ofo">Online feedback optimization</a></li>
  <li><a href="#mpc">Predictive control for large-scale systems</a></li>
  <li><a href="#arch">Theory of control architectures</a></li>
</ul>

<div class="publications">

<h2 id="game">Game-theoretic control</h2>
{% bibliography -q @*[topic=game] %}

<h2 id="hier">Hierarchical game theory for incentive design</h2>
{% bibliography -q @*[topic=hier] %}

<h2 id="ofo">Online feedback optimization</h2>
{% bibliography -q @*[topic=ofo] %}

<h2 id="mpc">Predictive control for large-scale systems</h2>
{% bibliography -q @*[topic=mpc] %}

<h2 id="arch">Theory of control architectures</h2>
{% bibliography -q @*[topic=arch] %}

</div>
