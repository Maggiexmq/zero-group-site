---
layout: about
title: Home
permalink: /
subtitle: KTH Royal Institute of Technology · Division of Decision and Control Systems

selected_papers: false # no paper list on the Home page
social: true # contact icons and address at the bottom of the page (edit _data/socials.yml and contact_note in _config.yml)

announcements:
  enabled: false # news is placed by hand below, next to "Who we are"
  scrollable: false
  limit: 4 # how many news items to show on the Home page

latest_posts:
  enabled: false
---

<link rel="stylesheet" href="{{ '/assets/css/zero.css' | relative_url }}">

<p class="zg-lead">
Our research focuses on the interplay of automatic control, optimization, and game theory, with applications to complex systems, especially large-scale infrastructures such as electrical power grids and transportation networks. Our goal is to improve their efficiency, reliability, and fairness.
</p>

<div class="zg-btns">
  <a class="zg-btn zg-btn-primary" href="{{ '/research/' | relative_url }}">Our research</a>
  <a class="zg-btn" href="{{ '/join/#phd' | relative_url }}">PhD position</a>
  <a class="zg-btn" href="{{ '/join/#postdoc' | relative_url }}">Postdoc position</a>
  <a class="zg-btn" href="{{ '/master/' | relative_url }}">Master projects</a>
</div>

<div class="zg-two zg-section">
  <div>
    <h2>Who we are</h2>
    <p>Zero Group is part of the Division of Decision and Control Systems at KTH Royal Institute of Technology in Stockholm. The group is led by Assistant Professor <a href="https://belgioio.github.io/">Giuseppe Belgioioso</a> and brings together PhD students, postdocs and research assistants working at the meeting point of automatic control, optimization and game theory.</p>
    <p>We are a rapidly growing team, with everyone either formally co-advised or integrated through various collaborations.</p>
  </div>
  <div class="zg-panel">
    <div class="zg-panel-head">
      <h3>Latest news</h3>
      <a href="{{ '/news/' | relative_url }}">All news →</a>
    </div>
    {% include news.liquid limit=true %}
  </div>
</div>

<div class="zg-grid zg-grid-3 zg-section">
  <a class="zg-card zg-hot" href="{{ '/join/' | relative_url }}">
    <span class="zg-label">Join us</span>
    <h3>Open positions</h3>
    <p><strong>Doctoral student</strong> in Game-Theoretic Methods for Multi-Agent Autonomous Systems · apply by Nov 1, 2026</p>
    <p><strong>Postdoc</strong> in Computational Methods for Games and Multi-Agent Decision Making · apply by Nov 5, 2026</p>
    <span class="zg-go">See positions →</span>
  </a>
  <a class="zg-card" href="{{ '/research/' | relative_url }}">
    <span class="zg-label">Research</span>
    <h3>What we work on</h3>
    <p>Online feedback optimization, game-theoretic control, incentive design, fairness in control, predictive control for large-scale systems, and theory of control architectures.</p>
    <span class="zg-go">Our research →</span>
  </a>
  <a class="zg-card" href="{{ '/people/' | relative_url }}">
    <span class="zg-label">People</span>
    <h3>The team</h3>
    <p>Meet the postdocs, PhD students and visitors who make up the group.</p>
    <span class="zg-go">Meet the team →</span>
  </a>
</div>

<h2 class="zg-section">Contact</h2>
