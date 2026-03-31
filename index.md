---
layout: default
title: OperationsPAI - Self-Evolving RCA Training Environment
---

<!-- Hero Section -->
<section class="hero">
  <div class="container">
    <div class="hero-content">
      <div class="hero-badge">Open Source Project</div>
      <h1 class="hero-title">
        World's First<br>
        <span class="highlight">Self-Evolving</span><br>
        RCA Training Environment
      </h1>
      <p class="hero-subtitle">
        Intelligent fault injection, algorithm evaluation, and microservice testing platform for building the next generation of root cause analysis systems.
      </p>
      <div class="btn-group">
        <a href="{{ '/docs/quickstart' | relative_url }}" class="btn btn-primary">
          Get Started →
        </a>
        <a href="https://github.com/OperationsPAI" class="btn btn-secondary" target="_blank">
          View on GitHub
        </a>
      </div>
    </div>
  </div>
</section>

<!-- Features Section -->
<section class="section">
  <div class="container">
    <div class="section-header">
      <p class="section-label">Core Capabilities</p>
      <h2 class="section-title">Platform Features</h2>
    </div>
    
    <div class="features-grid">
      <!-- Feature 1 -->
      <div class="tech-card">
        <div class="tech-card-header">
          <div class="tech-icon">⚡</div>
          <h3 class="tech-card-title">Intelligent Fault Injection</h3>
        </div>
        <p class="tech-card-desc">
          Advanced fault injection mechanisms that simulate real-world microservice failures. From network latency to cascading failures, test your RCA algorithms against production-like scenarios.
        </p>
      </div>
      
      <!-- Feature 2 -->
      <div class="tech-card">
        <div class="tech-card-header">
          <div class="tech-icon">📊</div>
          <h3 class="tech-card-title">Algorithm Evaluation</h3>
        </div>
        <p class="tech-card-desc">
          Comprehensive benchmarking framework for comparing RCA algorithms. Standardized metrics, reproducible experiments, and detailed performance analysis reports.
        </p>
      </div>
      
      <!-- Feature 3 -->
      <div class="tech-card">
        <div class="tech-card-header">
          <div class="tech-icon">🔬</div>
          <h3 class="tech-card-title">Microservice Testing</h3>
        </div>
        <p class="tech-card-desc">
          Production-grade microservice testbed with realistic service dependencies. Deploy, monitor, and analyze complex distributed systems in a controlled environment.
        </p>
      </div>
      
      <!-- Feature 4 -->
      <div class="tech-card">
        <div class="tech-card-header">
          <div class="tech-icon">🔄</div>
          <h3 class="tech-card-title">Self-Evolving System</h3>
        </div>
        <p class="tech-card-desc">
          Continuously expanding fault scenario library. The platform learns from new failure patterns and automatically generates challenging test cases for your algorithms.
        </p>
      </div>
      
      <!-- Feature 5 -->
      <div class="tech-card">
        <div class="tech-card-header">
          <div class="tech-icon">🎯</div>
          <h3 class="tech-card-title">Research Ready</h3>
        </div>
        <p class="tech-card-desc">
          Designed for academic research with proper citation support, experiment reproducibility, and integration with popular ML frameworks like PyTorch and TensorFlow.
        </p>
      </div>
      
      <!-- Feature 6 -->
      <div class="tech-card">
        <div class="tech-card-header">
          <div class="tech-icon">🌐</div>
          <h3 class="tech-card-title">Open Community</h3>
        </div>
        <p class="tech-card-desc">
          Active open-source community of researchers and engineers. Contribute algorithms, share experiments, and collaborate on advancing RCA technology.
        </p>
      </div>
    </div>
  </div>
</section>

<!-- Quick Start Section -->
<section class="section" style="background: var(--bg-secondary);">
  <div class="container">
    <div class="section-header">
      <p class="section-label">Installation</p>
      <h2 class="section-title">Quick Start</h2>
    </div>
    
    <div class="data-panel" style="max-width: 800px;">
      <div class="data-panel-header">
        <span class="data-panel-title">Terminal</span>
        <span class="status-indicator status-active">Ready</span>
      </div>
      <div class="code-block">
        <span class="comment"># Clone the repository</span><br>
        git clone https://github.com/OperationsPAI/OperationsPAI.git<br><br>
        <span class="comment"># Install dependencies</span><br>
        <span class="keyword">cd</span> OperationsPAI && pip install -r requirements.txt<br><br>
        <span class="comment"># Launch the training environment</span><br>
        python -m operationspai <span class="keyword">--mode</span> train
      </div>
    </div>
    
    <div style="margin-top: var(--space-xl); display: flex; gap: var(--space-xl); flex-wrap: wrap; justify-content: center;">
      <div class="metric">
        <span class="metric-value">50+</span>
        <span class="metric-label">Fault Scenarios</span>
      </div>
      <div class="metric">
        <span class="metric-value">100+</span>
        <span class="metric-label">GitHub Stars</span>
      </div>
      <div class="metric">
        <span class="metric-value">20+</span>
        <span class="metric-label">Contributors</span>
      </div>
    </div>
  </div>
</section>

<!-- Target Users Section -->
<section class="section">
  <div class="container">
    <div class="section-header">
      <p class="section-label">Audience</p>
      <h2 class="section-title">Built For</h2>
    </div>
    
    <div class="features-grid" style="grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));">
      <div class="tech-card tech-border">
        <div class="corner-accent top-left"></div>
        <div class="corner-accent bottom-right"></div>
        <h3 class="tech-card-title" style="color: var(--blueprint);">Researchers</h3>
        <p class="tech-card-desc">
          Academic researchers studying root cause analysis, anomaly detection, and distributed systems reliability.
        </p>
      </div>
      
      <div class="tech-card tech-border">
        <div class="corner-accent top-left"></div>
        <div class="corner-accent bottom-right"></div>
        <h3 class="tech-card-title" style="color: var(--alert);">Engineers</h3>
        <p class="tech-card-desc">
          Site reliability engineers and platform engineers building production monitoring and observability systems.
        </p>
      </div>
      
      <div class="tech-card tech-border">
        <div class="corner-accent top-left"></div>
        <div class="corner-accent bottom-right"></div>
        <h3 class="tech-card-title" style="color: var(--metal-light);">Students</h3>
        <p class="tech-card-desc">
          Students learning about distributed systems, chaos engineering, and machine learning for operations.
        </p>
      </div>
    </div>
  </div>
</section>

<!-- CTA Section -->
<section class="section" style="text-align: center;">
  <div class="container">
    <div class="section-header">
      <p class="section-label">Get Involved</p>
      <h2 class="section-title">Join the Community</h2>
    </div>
    
    <p style="font-family: var(--font-mono); color: var(--text-secondary); max-width: 600px; margin: 0 auto var(--space-xl);">
      Contribute to the future of root cause analysis. Whether you're improving algorithms, adding fault scenarios, or enhancing documentation, your contributions matter.
    </p>
    
    <div class="btn-group" style="justify-content: center;">
      <a href="https://github.com/OperationsPAI" class="btn btn-primary" target="_blank">
        Star on GitHub ★
      </a>
      <a href="{{ '/docs/contributing' | relative_url }}" class="btn btn-secondary">
        Contributing Guide
      </a>
    </div>
  </div>
</section>
