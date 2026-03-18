---
permalink: /
title: INTD 491 Student Project Showcase
body_class: home-page
---
<section class="hero-panel">
  <p class="page-kicker">INTD 491 showcase</p>
  <h1>Student projects, organized like a course archive.</h1>
  <p class="page-lead">Browse semester-based project pages with posters, repositories, demos, and documentation that students can extend through pull requests.</p>

  <div class="button-row">
    <a class="slate-button" href="{{ '/projects/' | relative_url }}">Browse projects</a>
    <a class="slate-button slate-button--secondary" href="{{ '/contributing/' | relative_url }}">Contribution guide</a>
  </div>
</section>

<section class="doc-card home-summary">
  <div>
    <h2>What this site contains</h2>
    <p>This repository publishes INTD 491 student work as a stable GitHub Pages archive. Each project gets its own detail page, and the main showcase at <a href="{{ '/projects/' | relative_url }}">/projects/</a> groups work by semester.</p>
    <p class="section-note">Students should add new projects by pull request using the template in <code>_projects/_TEMPLATE.md</code>.</p>
  </div>

  <div>
    <h2>Live archives</h2>
    <ul>
      <li><a href="{{ '/2026-spring/' | relative_url }}">Spring 2026</a></li>
      <li><a href="{{ '/2025-fall/' | relative_url }}">Fall 2025</a></li>
      <li><a href="{{ '/contributing/' | relative_url }}">Contribution guide</a></li>
    </ul>
  </div>
</section>
