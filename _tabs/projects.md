---
icon: fas fa-project-diagram
order: 4
---

<div class="projects-section">

<div class="project-card">
<details>
<summary>
<div class="project-header">
<h3>Doc-Orchestrator</h3>
<p class="project-tagline">AI-powered document orchestration agent for high-ROI workflows</p>
<div class="project-meta">
<span><i class="fas fa-calendar-alt"></i> Feb 2026</span>
<span><i class="fas fa-users"></i> Team (3) — AX Mission at Nota AI</span>
<span><i class="fas fa-user-tag"></i> Planning, Architecture, Development (85%)</span>
</div>
<div class="project-tags">
<span class="project-tag">Python</span>
<span class="project-tag">MCP</span>
<span class="project-tag">Claude Code</span>
<span class="project-tag">Confluence REST API</span>
<span class="project-tag">GPT-4o Transcribe</span>
</div>
</div>
</summary>

<div class="project-details">

A Claude Code skill that ingests meeting transcripts (audio/text), classifies content via dual classifiers, routes analysis to domain-specialized AI agents, and automatically updates Confluence documentation with safe section-level patching.

<div class="project-image">
<img src="/assets/img/projects/doc-orchestrator-architecture.png" alt="Doc-Orchestrator Architecture" loading="lazy">
</div>

#### Problem Solving 1 — Safe Section-Level Patching

- **Problem:** Confluence pages contain complex XML structures — full-page replacement via API destroys Jira macros, smart links, and collaborative metadata
- **Solution:** Built a custom MCP server (`confluence-helper`) that fetches raw storage-format XML, locates section boundaries by heading tags, replaces only the target section, and writes back atomically
- **Result:** Zero data loss on non-target sections; all metadata fully preserved

#### Problem Solving 2 — Domain Context Accuracy (v1 → v2)

- **Problem:** v1's general-purpose LLM analysis missed domain-specific nuances (e.g., confusing "lowering" across quantization vs graph optimization)
- **Solution:** Designed dual classifier + multi-agent architecture with 5 domain-specialized agents (Q, GO, MR, ME, SWE), each with built-in terminology glossaries
- **Result:** Domain-accurate analysis with correct disambiguation of overlapping terms

#### Key Contributions

- Designed dual MCP server architecture: standard mcp-atlassian for CRUD + custom confluence-helper for section patching
- Implemented 4 MCP tools: `confluence_patch_section`, `confluence_get_history`, `confluence_get_version_content`, `confluence_restore_version`
- Built 8-step orchestration flow: context → transcript → classification → analysis → search → proposal → approval → update
- Designed 5 domain-specialized AI agents with dedicated glossaries and reference page mappings
- Implemented dual classifier system (Topic × Part) for intelligent content routing

<div class="project-links">
<a href="https://github.com/nota-github/DOC-ORCHESTRATOR" target="_blank"><i class="fab fa-github"></i> GitHub</a>
</div>

</div>
</details>
</div>

<div class="project-card">
<details>
<summary>
<div class="project-header">
<h3>Gills Dream</h3>
<p class="project-tagline">AI-powered travel planner for MZ generation</p>
<div class="project-meta">
<span><i class="fas fa-calendar-alt"></i> Feb 2025 — Nov 2025</span>
<span><i class="fas fa-users"></i> Team (3) — Graduation Project</span>
<span><i class="fas fa-user-tag"></i> AI Lead & Backend Developer (33%)</span>
</div>
<div class="project-tags">
<span class="project-tag">Java</span>
<span class="project-tag">Spring</span>
<span class="project-tag">MySQL</span>
<span class="project-tag">Docker</span>
<span class="project-tag">Redis</span>
<span class="project-tag">AWS</span>
<span class="project-tag">FastAPI</span>
<span class="project-tag">OpenCV</span>
<span class="project-tag">OCR</span>
<span class="project-tag">RunPod GPU</span>
</div>
</div>
</summary>

<div class="project-details">

Users input YouTube Shorts URL + preferences → Video OCR analysis → Personalized itineraries with optimal routes via Map APIs.

<div class="project-image-row">
<img src="/assets/img/projects/gills-dream-profile.png" alt="Gills Dream App" loading="lazy">
<img src="/assets/img/projects/gills-dream-architecture.png" alt="Gills Dream Architecture" loading="lazy">
</div>

#### Problem Solving 1 — RunPod Serverless GPU

- **Problem:** OCR pipeline requires GPU compute, but usage is on-demand — persistent GPU instances waste resources
- **Solution:** Adopted RunPod Serverless GPU with event-driven worker allocation
- **Result:** ~85% GPU cost reduction

#### Problem Solving 2 — Redis Caching Layer

- **Problem:** OCR-extracted data immediately written to DB, causing unnecessary data accumulation before plan finalization
- **Solution:** Introduced Redis as interim cache — results stored temporarily, written to DB only after user finalizes
- **Result:** ~65% DB write reduction

#### Key Contributions

- Built Spring-based AWS infrastructure (EC2, VPC, RDS, S3)
- Implemented Spring Security + OAuth2 social login (Kakao, Apple) with Redis-based JWT session management
- Designed LLM API integration and travel plan generation via prompting
- Set up FastAPI server with Docker, deployed to RunPod Serverless GPU
- Built OCR pipeline: YouTube Shorts frame extraction → text recognition

<div class="project-links">
<a href="https://github.com/GILLs-Dream" target="_blank"><i class="fab fa-github"></i> GitHub</a>
<a href="https://apps.apple.com/kr/app/%EA%B8%B8%EB%8D%94%EC%9D%B4%EC%9D%98-%EA%BF%88/id6752535603?l=en-GB" target="_blank"><i class="fas fa-mobile-alt"></i> App Store</a>
</div>

</div>
</details>
</div>

<div class="project-card">
<details>
<summary>
<div class="project-header">
<h3>INFLUY</h3>
<p class="project-tagline">Personal select store for influencer sellers</p>
<div class="project-meta">
<span><i class="fas fa-calendar-alt"></i> May 2025 — Oct 2025</span>
<span><i class="fas fa-users"></i> Team (10) — CEOS IT Startup Club</span>
<span><i class="fas fa-user-tag"></i> Backend Lead (20%)</span>
</div>
<div class="project-tags">
<span class="project-tag">Java</span>
<span class="project-tag">Spring</span>
<span class="project-tag">MySQL</span>
<span class="project-tag">Docker</span>
<span class="project-tag">Redis</span>
<span class="project-tag">AWS</span>
<span class="project-tag">Grafana</span>
<span class="project-tag">Prometheus</span>
</div>
</div>
</summary>

<div class="project-details">

AI-powered TalkBox for automated customer inquiry classification and product Q&A — addressing Instagram-based commerce challenges.

<div class="project-image-row">
<img src="/assets/img/projects/influy-profile.png" alt="INFLUY App" loading="lazy">
<img src="/assets/img/projects/influy-architecture.png" alt="INFLUY Architecture" loading="lazy">
</div>

#### Problem Solving — Transaction Optimization

- **Problem:** LLM API-generated categories immediately saved to DB, then re-fetched by frontend — synchronous flow caused bottleneck
- **Solution:** Sent LLM-generated categories as JSON to frontend; deferred DB persistence until user completed customization
- **Result:** 30% DB query reduction, improved user response speed

#### Key Contributions

- Served as Backend Lead, advising on technical feasibility and system architecture
- Led internal backend meetings and coordinated sprint-based Agile development
- Built Spring-based AWS infrastructure and GitHub Actions CI/CD
- Designed LLM API integration and auto-classification for AI-powered TalkBox
- Built Prometheus + Grafana monitoring and conducted JMeter load testing
- **Selected for Promising Student Start-up Team 300+ (Growth Track A)**

<div class="project-links">
<a href="https://github.com/INFLUY/Influy-BE" target="_blank"><i class="fab fa-github"></i> GitHub</a>
</div>

</div>
</details>
</div>

<div class="project-card">
<details>
<summary>
<div class="project-header">
<h3>Silver Assistant</h3>
<p class="project-tagline">Multimodal real-time emergency detection system</p>
<div class="project-meta">
<span><i class="fas fa-calendar-alt"></i> Oct 2024 — Dec 2024</span>
<span><i class="fas fa-users"></i> Team (4) — NIPA-Google ML Bootcamp</span>
<span><i class="fas fa-user-tag"></i> Planning, Model Dev, Backend (40%)</span>
<span><i class="fas fa-trophy"></i> 3rd Place</span>
</div>
<div class="project-tags">
<span class="project-tag">FastAPI</span>
<span class="project-tag">Python</span>
<span class="project-tag">TensorFlow</span>
<span class="project-tag">YOLO</span>
<span class="project-tag">OpenCV</span>
<span class="project-tag">Transformer</span>
</div>
</div>
</summary>

<div class="project-details">

AI-powered elderly safety service — uses audio-only anomaly detection and activates the camera only when a risk event (falls, violence) is detected, then performs multimodal analysis to respond.

<div class="project-image-row">
<img src="/assets/img/projects/silver-assistant-flow.png" alt="Silver Assistant Service Flow" loading="lazy">
<img src="/assets/img/projects/silver-assistant-architecture.png" alt="Silver Assistant Architecture" loading="lazy">
</div>

#### Problem Solving — False Positive Resolution

- **Problem:** In daily scenes with 2+ people, the model predicted violence with 85%+ probability
- **Root Cause:** Model evaluated each person's pose independently without considering relative spatial relationships
- **Solution:** Extracted multi-person joint coordinates and vectorized relative position relationships as additional training features
- **Result:** Violence false-positives in daily scenes decreased significantly

#### Key Contributions

- Designed privacy-first service flow: audio anomaly detection activates camera only upon risk
- Collected and preprocessed video datasets for daily life, fall, and violence scenarios
- Modularized OpenCV frame processing + YOLO person detection → 33 joint keypoints extraction
- Developed Middle Fusion multimodal model (Transformer-based, TensorFlow) — **99.1% accuracy**

</div>
</details>
</div>

<div class="project-card">
<details>
<summary>
<div class="project-header">
<h3>Meme Sphere</h3>
<p class="project-tagline">Comprehensive meme coin platform with community features</p>
<div class="project-meta">
<span><i class="fas fa-calendar-alt"></i> Jan 2025 — Feb 2025</span>
<span><i class="fas fa-users"></i> Team (13) — UMC 7th Cohort</span>
<span><i class="fas fa-user-tag"></i> Backend Developer (10%)</span>
<span><i class="fas fa-trophy"></i> Grand Prize (1st / 69 teams)</span>
</div>
<div class="project-tags">
<span class="project-tag">Java</span>
<span class="project-tag">Spring</span>
<span class="project-tag">MySQL</span>
<span class="project-tag">Docker</span>
<span class="project-tag">Redis</span>
<span class="project-tag">AWS</span>
</div>
</div>
</summary>

<div class="project-details">

Real-time meme coin price tracking via Binance API, community, dashboard, search, and price alert system.

#### Problem Solving — Connection Bottleneck

- **Problem:** Periodic Binance API chart data collection caused traffic overload and connection bottleneck
- **Root Cause:** 21 meme coins + concurrent user requests generated 50+ parallel connections
- **Solution:** Tuned HikariCP connection pool capacity and idle timeout to match service traffic patterns
- **Result:** 100% data collection success rate

#### Key Contributions

- Designed Cron-based scheduler for periodic Binance API chart data collection across 21 coins
- Stored up to 6 data points per 10-min interval; designed DB load optimization structure
- Applied Soft-Delete for favorites and search features

<div class="project-links">
<a href="https://github.com/TeamMemeSphere/Backend-MemeSphere" target="_blank"><i class="fab fa-github"></i> GitHub</a>
</div>

</div>
</details>
</div>

</div>
