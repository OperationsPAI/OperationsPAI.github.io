---
layout: home
title: OperationsPAI - Self-Evolving RCA Training Environment
---

<!-- Hero Section -->
<section class="hero">
  <div class="hero-content">
    <div class="hero-badge">
      <span class="dot"></span>
      Open Source Community
    </div>

    <h1>World's First <em>Self-Evolving</em> RCA Training Environment</h1>

    <p class="hero-tagline">
      Intelligent fault injection, algorithm evaluation, and microservice testing
      for building the next generation of root cause analysis systems.
    </p>

    <div class="hero-actions">
      <a href="https://github.com/OperationsPAI" class="btn btn-primary" target="_blank" rel="noopener">
        Join on GitHub
      </a>
      <a href="{{ '/docs/community/vision.html' | relative_url }}" class="btn btn-ghost">
        Explore Vision
      </a>
    </div>
  </div>

  {% include svg/hero-network.html %}
</section>

<!-- Core Capabilities -->
<section class="section">
  <div class="section-header">
    <span class="section-label">Core Capabilities</span>
    <h2 class="section-title">Intelligent. Adaptive. Evolving.</h2>
    <p class="section-desc">
      Our platform combines cutting-edge AI with real-world microservice architectures
      to create the ultimate training ground for root cause analysis.
    </p>
  </div>

  <div class="grid grid-auto">
    <div class="card">
      {% include svg/icon-lightning.html %}
      <h3>Intelligent Fault Injection</h3>
      <p>Advanced fault injection that simulates real-world microservice failures.
        From network latency to cascading failures, test against production-like scenarios.</p>
    </div>

    <div class="card">
      {% include svg/icon-waveform.html %}
      <h3>Algorithm Evaluation</h3>
      <p>Comprehensive benchmarking framework for comparing RCA algorithms.
        Standardized metrics, reproducible experiments, and detailed analysis.</p>
    </div>

    <div class="card">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
        <rect x="2" y="3" width="20" height="14" rx="2" ry="2"/>
        <line x1="8" y1="21" x2="16" y2="21"/>
        <line x1="12" y1="17" x2="12" y2="21"/>
      </svg>
      <h3>Microservice Testing</h3>
      <p>Production-grade testbed with realistic service dependencies.
        Deploy, monitor, and analyze distributed systems in a controlled environment.</p>
    </div>

    <div class="card">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
        <path d="M12 2v4"/><path d="M12 18v4"/>
        <path d="M4.93 4.93l2.83 2.83"/><path d="M16.24 16.24l2.83 2.83"/>
        <path d="M2 12h4"/><path d="M18 12h4"/>
        <path d="M4.93 19.07l2.83-2.83"/><path d="M16.24 7.76l2.83-2.83"/>
      </svg>
      <h3>Self-Evolving System</h3>
      <p>Continuously expanding fault scenario library. The platform learns from new failure patterns
        and automatically generates challenging test cases.</p>
    </div>

    <div class="card">
      {% include svg/icon-book.html %}
      <h3>Research Ready</h3>
      <p>Designed for academic research with citation support, experiment reproducibility,
        and integration with PyTorch and TensorFlow.</p>
    </div>

    <div class="card">
      {% include svg/icon-community.html %}
      <h3>Open Community</h3>
      <p>Active community of researchers and engineers.
        Contribute algorithms, share experiments, and collaborate on advancing RCA.</p>
    </div>
  </div>
</section>

<!-- Evolution -->
<section class="section" style="background: var(--bg-secondary); margin: 0 calc(-1 * var(--space-lg)); padding-left: var(--space-lg); padding-right: var(--space-lg);">
  <div class="section-header" style="text-align: center;">
    <span class="section-label">The Evolution</span>
    <h2 class="section-title">From Static to Living Systems</h2>
    <p class="section-desc" style="margin-left: auto; margin-right: auto;">
      Traditional RCA tools are static. OperationsPAI evolves.
    </p>
  </div>

  <div class="timeline">
    <div class="timeline-step">
      <div class="timeline-number">01</div>
      <div class="timeline-label">Inject</div>
    </div>
    <div class="timeline-arrow">&#8594;</div>
    <div class="timeline-step">
      <div class="timeline-number">02</div>
      <div class="timeline-label">Observe</div>
    </div>
    <div class="timeline-arrow">&#8594;</div>
    <div class="timeline-step">
      <div class="timeline-number">03</div>
      <div class="timeline-label">Analyze</div>
    </div>
    <div class="timeline-arrow">&#8594;</div>
    <div class="timeline-step">
      <div class="timeline-number">04</div>
      <div class="timeline-label">Adapt</div>
    </div>
  </div>
</section>

<!-- CTA -->
<section class="section" style="text-align: center;">
  <h2 class="section-title">Ready to Evolve?</h2>
  <p class="section-desc" style="margin-left: auto; margin-right: auto;">
    Join our community of researchers and engineers building the future
    of root cause analysis.
  </p>
  <div class="hero-actions" style="justify-content: center;">
    <a href="{{ '/CONTRIBUTING.html' | relative_url }}" class="btn btn-primary">
      Start Contributing
    </a>
    <a href="{{ '/docs/FAQ.html' | relative_url }}" class="btn btn-ghost">
      Read FAQ
    </a>
  </div>
</section>

<!-- Quick Links -->
<section class="section">
  <div class="section-header">
    <span class="section-label">Documentation</span>
    <h2 class="section-title">Explore Our Resources</h2>
  </div>

  <div class="grid grid-auto">
    <a href="{{ '/docs/community/vision.html' | relative_url }}" class="card">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
        <circle cx="12" cy="12" r="10"/>
        <line x1="12" y1="16" x2="12" y2="12"/>
        <line x1="12" y1="8" x2="12.01" y2="8"/>
      </svg>
      <h3>Vision &amp; Mission</h3>
      <p>Our long-term goals and the future we are building towards.</p>
    </a>

    <a href="{{ '/ROADMAP.html' | relative_url }}" class="card">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
        <line x1="18" y1="20" x2="18" y2="10"/>
        <line x1="12" y1="20" x2="12" y2="4"/>
        <line x1="6" y1="20" x2="6" y2="14"/>
      </svg>
      <h3>Project Roadmap</h3>
      <p>Timeline, milestones, and upcoming features.</p>
    </a>

    <a href="{{ '/CONTRIBUTING.html' | relative_url }}" class="card">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
        <line x1="12" y1="5" x2="12" y2="19"/>
        <line x1="5" y1="12" x2="19" y2="12"/>
      </svg>
      <h3>Contributing Guide</h3>
      <p>How to get involved and make an impact.</p>
    </a>

    <a href="{{ '/docs/FAQ.html' | relative_url }}" class="card">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
        <circle cx="12" cy="12" r="10"/>
        <path d="M9.09 9a3 3 0 0 1 5.83 1c0 2-3 3-3 3"/>
        <line x1="12" y1="17" x2="12.01" y2="17"/>
      </svg>
      <h3>FAQ</h3>
      <p>Frequently asked questions and answers.</p>
    </a>
  </div>
</section>
