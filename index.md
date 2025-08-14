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

<section class="py-5 bg-light">
  <div class="container">
    <div class="row g-5 text-center align-items-start feature-icons">
      <div class="col-md-4">
        <div class="feature-icon mx-auto mb-3" aria-hidden="true">
          <!-- window icon -->
          <svg width="56" height="56" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6">
            <rect x="3" y="4" width="18" height="16" rx="2" ry="2"></rect>
            <line x1="3" y1="8" x2="21" y2="8"></line>
            <circle cx="6" cy="6" r="0.8"></circle>
            <circle cx="9" cy="6" r="0.8"></circle>
            <circle cx="12" cy="6" r="0.8"></circle>
          </svg>
        </div>
        <h3 class="h4 fw-bold">Fully Responsive</h3>
        <p class="text-muted mb-0">Looks great on any device, large or small.</p>
      </div>

      <div class="col-md-4">
        <div class="feature-icon mx-auto mb-3" aria-hidden="true">
          <!-- layers icon -->
          <svg width="56" height="56" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6">
            <polygon points="12 2 22 8 12 14 2 8 12 2"></polygon>
            <polyline points="2 12 12 18 22 12"></polyline>
            <polyline points="2 16 12 22 22 16"></polyline>
          </svg>
        </div>
        <h3 class="h4 fw-bold">Bootstrap 5 Ready</h3>
        <p class="text-muted mb-0">Uses the latest Bootstrap utilities and grid.</p>
      </div>

      <div class="col-md-4">
        <div class="feature-icon mx-auto mb-3" aria-hidden="true">
          <!-- terminal icon -->
          <svg width="56" height="56" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6">
            <polyline points="4 7 9 12 4 17"></polyline>
            <line x1="11" y1="17" x2="20" y2="17"></line>
            <rect x="2.5" y="4.5" width="19" height="15" rx="2"></rect>
          </svg>
        </div>
        <h3 class="h4 fw-bold">Easy to Use</h3>
        <p class="text-muted mb-0">Drop in your content; publishing is automated.</p>
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
