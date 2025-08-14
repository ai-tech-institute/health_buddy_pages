---
layout: default
title: Health Buddy — AI-Powered Health Insights
---

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
<link rel="stylesheet" href="{{ '/assets/styles.css' | relative_url }}">

<section class="py-5 bg-light text-center hero">
  <div class="container">
    <h1 class="display-5 fw-bold">Generate more insights with a trusted health research companion</h1>
    <p class="lead mt-3">Weekly summaries and daily updates, curated by AI for patients, caregivers, and professionals. Let Health Buddy do the research for YOU!</p>
    <div class="mt-4">
      <a href="{{ '/subscribe' | relative_url }}" class="btn btn-primary btn-lg px-4">Subscribe — 100% Free</a>
    </div>
  </div>
</section>

<section class="py-5">
  <div class="container">
    <h2 class="mb-4">Why Health Buddy</h2>
    <ul class="list-group list-group-flush fs-5 benefits-list">
      <li class="list-group-item d-flex align-items-start">
        <span class="badge bg-success rounded-pill me-3">1</span>
        <div><strong>Dig</strong> — AI searches journals and clinical trials daily.</div>
      </li>
      <li class="list-group-item d-flex align-items-start">
        <span class="badge bg-success rounded-pill me-3">2</span>
        <div><strong>Highlight</strong> — Filters key breakthroughs.</div>
      </li>
      <li class="list-group-item d-flex align-items-start">
        <span class="badge bg-success rounded-pill me-3">3</span>
        <div><strong>Refine</strong> — Ensures accuracy iteratively.</div>
      </li>
      <li class="list-group-item d-flex align-items-start">
        <span class="badge bg-success rounded-pill me-3">4</span>
        <div><strong>Daily Insights</strong> — Clear, simplified reports.</div>
      </li>
      <li class="list-group-item d-flex align-items-start">
        <span class="badge bg-success rounded-pill me-3">5</span>
        <div><strong>Wrap Up</strong> — Weekly summary tailored for you.</div>
      </li>
    </ul>
  </div>
</section>

<section class="py-5 bg-light">
  <div class="container">
    <h2 class="mb-4">Topics</h2>
    <div class="row g-3">
      {% for t in site.data.topics.topics %}
      <div class="col-md-6 col-lg-4">
        <a class="list-group-item list-group-item-action p-3 shadow-sm d-block rounded text-decoration-none"
           href="{{ '/topics/' | append: t.slug | append: '/' | relative_url }}">
          <span class="fw-semibold">{{ t.display }}</span>
        </a>
      </div>
      {% endfor %}
      {% if site.data.topics.topics == nil or site.data.topics.topics.size == 0 %}
      <p class="text-muted">No topics available yet.</p>
      {% endif %}
    </div>
  </div>
</section>

<section class="py-5">
  <div class="container">
    <h2 class="mb-4">Recent Daily Reports</h2>
    <div class="row g-4">
      {% assign recent = site.daily_reports | sort: 'date' | reverse | slice: 0, 6 %}
      {% for r in recent %}
      {% assign persona_clean = r.persona | default: '' | replace: '_', ' ' | capitalize %}
      {% assign preview = r.content | strip_html | strip_newlines | truncate: 180 %}
      <div class="col-md-6 col-lg-4">
        <div class="card h-100 shadow-sm">
          <div class="card-body">
            <h3 class="card-title h6 mb-2">
              <a class="stretched-link text-decoration-none" href="{{ r.url | relative_url }}">{{ r.topic_display }}</a>
            </h3>
            <p class="card-text small mb-2">
              {{ r.date | date: '%Y-%m-%d' }}{% if persona_clean %} • {{ persona_clean }}{% endif %}{% if r.theme %} • {{ r.theme }}{% endif %}
            </p>
            <p class="card-text clamp-3">{{ preview }}</p>
          </div>
        </div>
      </div>
      {% endfor %}
      {% if recent == empty %}
      <p class="text-muted">No daily reports yet for this period.</p>
      {% endif %}
    </div>
  </div>
</section>

<section class="py-5 bg-primary text-white text-center">
  <div class="container">
    <h2 class="mb-3">Ready to get started?</h2>
    <p class="lead mb-4">Subscribe now to receive free weekly summaries and daily insights.</p>
    <a href="{{ '/subscribe' | relative_url }}" class="btn btn-light btn-lg px-4">Subscribe</a>
  </div>
</section>
