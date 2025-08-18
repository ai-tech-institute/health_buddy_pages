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
      <a href="{{ site.subscribe_url }}" target="_blank" rel="noopener" class="btn btn-primary btn-lg px-4">Subscribe — 100% FREE!</a>
    </div>
    <p class="lead mt-3"> No Credit Card, No Password Required! </p>
    <p class="lead mt-3"> Why free? This complimentary service is provided by the Fairfield AI & Tech Institute whose motto is "AI for the Greater Good"! Read more about the institute here. </p>
  </div>
</section>

<section class="py-5 bg-light">
  <div class="container">
    <div class="row g-5 text-center align-items-start feature-icons">
      <!-- 1. Dig -->
      <div class="col-md-6 col-lg-4">
        <div class="feature-icon mx-auto mb-3" aria-hidden="true">
          <!-- search icon -->
          <svg width="56" height="56" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6">
            <circle cx="11" cy="11" r="7"></circle>
            <line x1="21" y1="21" x2="16.65" y2="16.65"></line>
          </svg>
        </div>
        <h3 class="h4 fw-bold">Dig</h3>
        <p class="text-muted mb-0">AI searches journals and clinical trials daily.</p>
      </div>

      <!-- 2. Highlight -->
      <div class="col-md-6 col-lg-4">
        <div class="feature-icon mx-auto mb-3" aria-hidden="true">
          <!-- star icon -->
          <svg width="56" height="56" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6">
            <polygon points="12 2 15 9 22 9 16.5 13.5 18.5 21 12 16.8 5.5 21 7.5 13.5 2 9 9 9 12 2"></polygon>
          </svg>
        </div>
        <h3 class="h4 fw-bold">Highlight</h3>
        <p class="text-muted mb-0">Filters key breakthroughs that matter.</p>
      </div>

      <!-- 3. Refine -->
      <div class="col-md-6 col-lg-4">
        <div class="feature-icon mx-auto mb-3" aria-hidden="true">
          <!-- shield-check icon -->
          <svg width="56" height="56" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6">
            <path d="M12 3l7 4v5c0 5-3.5 8-7 9-3.5-1-7-4-7-9V7l7-4z"></path>
            <polyline points="9 12 11 14 15 10"></polyline>
          </svg>
        </div>
        <h3 class="h4 fw-bold">Refine</h3>
        <p class="text-muted mb-0">Ensures accuracy with iterative checks.</p>
      </div>

      <!-- 4. Daily Insights -->
      <div class="col-md-6 col-lg-4">
        <div class="feature-icon mx-auto mb-3" aria-hidden="true">
          <!-- file-text icon -->
          <svg width="56" height="56" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6">
            <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"></path>
            <polyline points="14 2 14 8 20 8"></polyline>
            <line x1="16" y1="13" x2="8" y2="13"></line>
            <line x1="16" y1="17" x2="8" y2="17"></line>
          </svg>
        </div>
        <h3 class="h4 fw-bold">Daily Insights</h3>
        <p class="text-muted mb-0">Clear, simplified daily reports.</p>
      </div>

      <!-- 5. Wrap Up -->
      <div class="col-md-6 col-lg-4">
        <div class="feature-icon mx-auto mb-3" aria-hidden="true">
          <!-- calendar icon -->
          <svg width="56" height="56" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6">
            <rect x="3" y="4" width="18" height="18" rx="2"></rect>
            <line x1="16" y1="2" x2="16" y2="6"></line>
            <line x1="8" y1="2" x2="8" y2="6"></line>
            <line x1="3" y1="10" x2="21" y2="10"></line>
          </svg>
        </div>
        <h3 class="h4 fw-bold">Wrap Up</h3>
        <p class="text-muted mb-0">Weekly summary tailored for you.</p>
      </div>

      <!-- 6. Personalized Guidance -->
      <div class="col-md-6 col-lg-4">
        <div class="feature-icon mx-auto mb-3" aria-hidden="true">
          <!-- user icon -->
          <svg width="56" height="56" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6">
            <circle cx="12" cy="7" r="4"></circle>
            <path d="M5.5 20a6.5 6.5 0 0 1 13 0"></path>
          </svg>
        </div>
        <h3 class="h4 fw-bold">Personalized Guidance</h3>
        <p class="text-muted mb-0">Tailors hard-to-find insights to you.</p>
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
      <div class="col-md-6 col-lg-4">
        <div class="card h-100 shadow-sm">
          <div class="card-body">
            <h3 class="card-title h6 mb-2">
              <a class="text-decoration-none d-inline-flex align-items-center" href="{{ r.url | relative_url }}">
                <svg class="link-icon me-2" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M10 13a5 5 0 0 1 0-7l1-1a5 5 0 0 1 7 7l-1 1"></path>
                  <path d="M14 11a5 5 0 0 1 0 7l-1 1a5 5 0 0 1-7-7l1-1"></path>
                </svg>
                {{ r.topic_display }}
              </a>
            </h3>
            <p class="card-text small mb-0">
              {{ r.date | date: '%Y-%m-%d' }}{% if persona_clean %} • {{ persona_clean }}{% endif %}{% if r.theme %} • {{ r.theme }}{% endif %}
            </p>
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
    <a href="{{ site.subscribe_url }}" target="_blank" rel="noopener" class="btn btn-light btn-lg px-4">Subscribe</a>
  </div>
</section>
