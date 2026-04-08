---
layout: default
title: Home
---

<div class="hero">
  <h1>Morning <span class="accent">AI</span> Daily<span class="cursor">_</span></h1>
  <p class="tagline">AI industry tracking — models, products, benchmarks, funding</p>
  <div class="stats">
    <div class="stat-card">
      <div class="stat-label">Entities</div>
      <div class="stat-value">76+</div>
    </div>
    <div class="stat-card">
      <div class="stat-label">Sources</div>
      <div class="stat-value">9</div>
    </div>
    <div class="stat-card">
      <div class="stat-label">Types</div>
      <div class="stat-value">4</div>
    </div>
    <div class="stat-card">
      <div class="stat-label">Reports</div>
      <div class="stat-value green">{{ site.pages | where: "layout", "report" | size }}</div>
    </div>
  </div>
</div>

<section>
  <p class="section-label"><span class="prompt">></span> REPORT TIMELINE</p>
  <div class="timeline">
    {% assign reports = site.pages | where: "layout", "report" | sort: "name" | reverse %}
    {% assign current_month = "" %}
    {% for report in reports %}
      {% assign month = report.name | slice: 0, 7 %}
      {% if month != current_month %}
        {% assign current_month = month %}
        <div class="timeline-month">{{ month }}</div>
      {% endif %}
      {% assign date = report.name | remove: ".md" %}
      <a href="{{ report.url | relative_url }}" class="timeline-item">
        <div class="timeline-marker">
          <div class="timeline-dot"></div>
          <div class="timeline-line"></div>
        </div>
        <div class="timeline-card">
          <div class="timeline-date">{{ date }}</div>
          {% if report.summary %}
            <div class="timeline-summary">{{ report.summary }}</div>
          {% endif %}
          <span class="timeline-link">view report &rarr;</span>
        </div>
      </a>
    {% endfor %}
  </div>
</section>
