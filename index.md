---
layout: default
title: Health Buddy — AI-Powered Health Insights
---

<!-- Bootstrap 5 CSS -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
<link rel="stylesheet" href="{{ '/assets/styles.css' | relative_url }}">

<section class="py-5 bg-light text-center hero">
  <div class="container">
    <h1 class="display-5 fw-bold">Generate more insights with a trusted health research companion</h1>
    <p class="lead mt-3">Weekly summaries and daily updates, curated by AI for patients, caregivers, and professionals.</p>
    <div class="mt-4">
      <a href="{{ '/subscribe' | relative_url }}" class="btn btn-primary btn-lg px-4">Subscribe — 100% Free</a>
    </div>
  </div>
</section>

<section class="py-5">
  <div class="container">
    <div class="row g-4 text-center">
      <div class="col-md-4">
        <div class="card h-100 shadow-sm">
          <div class="card-body">
            <h3 class="card-title h5">Fully Responsive</h3>
            <p class="card-text">Looks great on any device, with clean, readable content.</p>
          </div>
        </div>
      </div>
      <div class="col-md-4">
        <div class="card h-100 shadow-sm">
          <div class="card-body">
            <h3 class="card-title h5">AI‑Powered</h3>
            <p class="card-text">Daily research, weekly wrap‑ups, and clear takeaways you can act on.</p>
          </div>
        </div>
      </div>
      <div class="col-md-4">
        <div class="card h-100 shadow-sm">
          <div class="card-body">
            <h3 class="card-title h5">Easy to Use</h3>
            <p class="card-text">Subscribe in seconds. New reports appear automatically here.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="py-5 bg-light">
  <div class="container">
    <h2 class="mb-4">Topics</h2>
    <div class="row g-3">
      {% for t in site.data.topics.topics %}
      <div class="col-md-6 col-lg-4">
        <a class="list-group-item list-group-item-action p-3 shadow-sm d-block rounded text-decoration-none" href="{{ '/topics/' | append: t.slug | append: '/' | relative_url }}">
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
      <div class="col-md-6 col-lg-4">
        <div class="card h-100 shadow-sm">
          <div class="card-body">
            <h3 class="card-title h6 mb-2"><a class="stretched-link text-decoration-none" href="{{ r.url }}">{{ r.topic_display }}</a></h3>
            <p class="card-text small mb-1">{{ r.date }}{% if r.persona %} • {{ r.persona }}{% endif %}{% if r.theme %} • {{ r.theme }}{% endif %}</p>
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

<!-- Optional Bootstrap JS (not required for this page) -->
