---
layout: home
title: Health Buddy — AI-Powered Health Insights
---

<link rel="stylesheet" href="{{ '/assets/styles.css' | relative_url }}">

<header class="hero">
  <h1>Take Action on Your Health</h1>
  <p>Health Buddy is here to help — designed for YOU by Fairfield Dolan AI & Tech Institute</p>
  <a href="{{ '/subscribe' | relative_url }}" class="cta-button">Subscribe Now — 100% Free!</a>
</header>

<section class="benefits">
  <div class="benefit-card">100% Free Access</div>
  <div class="benefit-card">24/7 AI Research</div>
  <div class="benefit-card">1 Weekly Report</div>
</section>

<section class="how-it-works">
  <h2>How Health Buddy Works</h2>
  <div class="steps">
    <div class="step">1. Free Subscription</div>
    <div class="step">2. AI Agentic Research</div>
    <div class="step">3. Free Reports</div>
  </div>
</section>

<section class="topics">
  <h2>Topics</h2>
  <ul class="topic-list">
    {% for t in site.data.topics.topics %}
      <li><a href="{{ '/topics/' | append: t.slug | append: '/' | relative_url }}">{{ t.display }}</a></li>
    {% endfor %}
  </ul>
</section>

<section class="final-cta">
  <h2>Subscribe Now!</h2>
  <p>AI-powered medical updates — 100% free!</p>
  <a href="{{ '/subscribe' | relative_url }}" class="cta-button">Get Started</a>
</section>
