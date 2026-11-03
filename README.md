# Hi, I'm Soundarya Dash

**Senior Software Engineer · ML Engineer · AI Agent Governance · Agentic AI**

Philadelphia, PA · [dashsoundarya12@gmail.com](mailto:dashsoundarya12@gmail.com) · linkedin.com/in/soundarya-dash · [Devpost portfolio](https://devpost.com/dashsoundarya?ref_content=user-portfolio&ref_feature=portfolio&ref_medium=global-nav) · [github.com/codergirl73/codergirl73](https://github.com/codergirl73/codergirl73)

## About me

Senior Software Engineer and ML Engineer with 6+ years shipping enterprise distributed systems, agentic AI platforms, and production RAG pipelines at JPMorgan Chase, Thomson Reuters, and Jio Platforms.

Currently building neurosymbolic agent governance at Sondera AI — policy-as-code enforced on every agent action, with monitoring and human escalation.

M.S. Computer Science, Temple University (GPA 3.64, expected May 2027), with a focus on applied machine learning, interpretable AI, and deep learning.

My work follows one principle: let the model read, explain, and draft — and let deterministic code verify, score, and decide. That pattern runs through everything below, from prior-authorization checks and claim verification to incident agents that are only allowed to merge a fix when a policy gate, not the agent, says so.

### What I work on

- **Agent governance and security** — neurosymbolic policy enforcement, autoformalization, policy-as-code, trajectory scanning, monitor agents, human-in-the-loop escalation, prompt-injection defenses, and audit trails an independent reviewer can re-check.
- **Agentic AI systems** — multi-agent orchestration with LangGraph, MCP servers and MCP Apps, tool-use loops with explicit consent locks, and agents that surface their work instead of acting silently.
- **Production ML and RAG** — RAG pipelines over large document sets, document extraction with human quality gates, interpretable ML, and LLM automation deployed inside enterprise controls (PII redaction, RBAC, least-privilege access).

## Current work — Sondera AI

**Full Stack Developer Intern, Sondera AI** · Philadelphia, PA · Jun 2026 – Present
*Rust · Python · GCP · Svelte · React*

Sondera is a neurosymbolic agent governance platform: natural-language organisational rules are compiled into formally verified policy-as-code, and that policy is enforced on every agent action, across any runtime or harness.

- Contribute to the autoformalization engine that compiles natural-language rules into formally verified policy-as-code; contribute Rust evaluation components, using memory safety and zero-cost abstractions for provable correctness at agent runtime.
- Engineered a trajectory scanner grounded in four reliability pillars — correctness, safety, efficiency, compliance — with a monitor agent that surfaces violations or escalates to a human.
- Built Policy Studio (Svelte/React + GCP) for authoring, simulating, versioning, and auditing policies, with rubric-driven evaluation logic for reviewing policies end to end.
- Built an Ops Dashboard with enforcement metrics, violation trends, and forensic proof trails, so a production AI deployment can be signed off with evidence rather than trust.

## Experience

### Software Engineer III — JPMorgan Chase & Co. · Bengaluru, India · Oct 2022 – Aug 2025

*LangGraph · GPT-4 · RAG · AWS · Terraform · Spring Boot · Kafka*

- Architected a LangGraph multi-agent system converting Figma wireframes to JIRA stories — 85% accuracy, 65% faster story creation across 15+ teams — with least-privilege IAM and prompt-injection defenses throughout. The multi-agent design split the work across a design component extractor, a user flow analyzer, and an acceptance criteria generator, with bidirectional sync between Figma designs and JIRA.
- Deployed secured LLM incident automation (LangGraph + GPT-4) with human-in-the-loop feedback loops — 90% severity accuracy, 70% less manual incident creation.
- Built a production RAG pipeline over 10,000+ docs as a ServiceNow chatbot — 90% categorization accuracy, 60% faster ticket creation — with automated ticket creation, team-expertise routing, priority classification, and enterprise controls: PII redaction before LLM ingestion, RBAC, and comprehensive audit trails.
- Architected the Salesforce Client Data Model via Kinesis and EventBridge (95% sync accuracy, 60% latency reduction), with the full AWS infrastructure managed via Terraform IaC.
- Designed event-driven microservices processing $10M+/day in transactions, achieving 50% latency reduction via async pipelines, intelligent caching, and query optimization.
- Won the 2024 internal Hackathon with an AI/ML task management tool using NLP intent detection and collaborative filtering across Outlook, Teams, and OneNote.

### Software Engineer II — Thomson Reuters · Bengaluru, India · May 2021 – Oct 2022

*Intelligent Document Processing · AWS Textract · Lambda · Step Functions · Python · CloudWatch*

- Engineered a human-in-the-loop AI document pipeline (AWS Textract + FineReader) processing 10,000+ legal docs/day at 95% extraction accuracy, with automated quality validation gates flagging low-confidence extractions for human review.
- Designed a serverless ML workflow (Lambda + Step Functions + API Gateway) for parallel document processing — 150% throughput improvement, 45% error reduction, 99.5% SLA maintained via proactive CloudWatch monitoring and alerting.
- Built robust Python automation workflows with retry mechanisms and error handling, integrating downstream REST APIs and message queues across 8+ internal systems.

### Software Developer — Jio Platforms Ltd. · Navi Mumbai, India · Aug 2019 – May 2021

*Full-Stack · Kafka · MongoDB · Redis · WebSockets · React · Java · Spring Boot*

- Developed a full-stack Electronic Medical Records system serving 100,000+ concurrent users — Kafka event streaming for real-time data sync, MongoDB for flexible storage, Redis for session management, and WebSocket live notifications — across 5 hospital networks.
- Designed and delivered RESTful microservices in Spring Boot for patient data, appointment scheduling, and billing modules.
- Cut load time 40% via performance profiling and optimization: code splitting, lazy loading, API response caching, database query optimization with indexing, and CDN deployment.

## Projects

All of these follow the same rule from my day job — the model proposes, deterministic code disposes.

### CalmFix — `gitlab/calmfix`

[GitLab showcase](https://gitlab.com/gitlab-ai-hackathon/transcend-october-2026/43456551/showcase) · [Devpost](https://devpost.com/software/calmfix)
*Python 3.12 · FastAPI · GitLab Duo Agent Platform · Cloud Run · Terraform · Docker · pytest*

An incident-to-fix loop for a production service on Cloud Run. A policy file, `.agent-policy.yml`, sets what agents may do alone; a triage agent finds the suspect commit and opens a fix MR, and a guardian agent reviews it against the policy.

- Agents have no merge tool — a merge governor merges only an approved MR with a green pipeline, then a 10% canary promotes or rolls back on its own. Every decision goes into a hash-chained audit log.
- **Results:** two real incidents resolved with no human in the loop, including one that failed its canary at p95 1347 ms against an 800 ms limit, rolled back, and was then fixed. 58 passing tests.

### AuthAssist — `github/authassist`

[Devpost](https://devpost.com/software/authassist)
*Python · FastAPI · NVIDIA Nemotron (via Nebius Token Factory) · Tavily · Pydantic · ReportLab · Docker*

Checks a clinical note against the insurer's current published policy for prior authorization (MRI lumbar spine, CPT 72148) and shows exactly what evidence is missing, before the insurer does. Nothing is ever submitted to an insurer.

- Code verifies every evidence quote appears word-for-word in the note and computes the readiness score itself — never the LLM. Nemotron models are routed by role: Ultra for reasoning, Nano for fast extraction, a vision model for faxed scans.
- **Results:** 8/8 correct outcomes on 8 synthetic cases, 100% of evidence quotes verified verbatim, with a gap-fill loop that moved one case's score from 33 to 100.

### Unrush — `github/unrush`

[Devpost](https://devpost.com/software/unrush-2g3fo1)
*TypeScript · MCP · Amazon Bedrock · AgentCore Memory · React · SQLite*

A proactive household assistant (a simulated Alexa+ experience in the browser) that speaks first when a late meeting breaks an evening — working departure time, dinner, and groceries in order. It never spends money without asking.

- Self-hosted MCP server with 17 tools and a proactive engine that detects a squeezed departure or a dinner that no longer fits, using plain arithmetic for leave-by times and staple run-out.
- **Consent by design:** three independent locks before any order — the tool requires `confirmed: true`, the backend requires a clear yes, and app views are read-only. 95 automated tests.

### TrustCheck — `devpost/trustcheck`

[Devpost](https://devpost.com/software/trustcheck-vrwz86)
*TypeScript · Gemini / Vertex AI · React · Node.js · Express · PostgreSQL*

Fact-checks money claims, scam emails, and headlines, showing the evidence rather than the hype. It never gives financial advice and never says buy or sell.

- Every verdict is decided in code from tier-weighted evidence (Tier 1 primary sources = 3, Tier 2 established news = 2, Tier 3 = 0.5, capped), and the app does claim math itself — "5% every week" becomes the yearly return it implies. Also includes an email scam check and ScamSOS, a rules-first safety plan linked to FTC / FBI IC3 guidance.
- **Results:** 224 unit tests covering tiering, math, verdicts, validators, and email signals.

### Gatherly — `github/gatherly`

[Devpost](https://devpost.com/software/gatherly-rm0hbu)
*Next.js · TypeScript · Qloo · Gemini · Supabase · Tailwind · Vercel*

A group-event agent that treats taste as data: describe the night, add 3–6 people and what each one loves, and it plans a night where every pick can show its work. It never books or pays for anything.

- Gemini runs a tool-use loop over Qloo taste data, and a grounding validator in code checks that every pick's entity ID was actually returned by Qloo and limits each pick's "fits" to real group members.
- **Results:** in one live run, 7 of 7 Qloo picks traced to real data versus 0 of 8 for an LLM-only plan. 33 unit tests plus a live suite of 7 tests against the real Qloo API.

### OwlSpeaks — AI Finance Trading Platform — `github/owls-street`

[GitHub — OpenOwls-at-Temple/owls-street](https://github.com/OpenOwls-at-Temple/owls-street)
*Python · React · LangChain · RAG · TradingView-style charting*

Co-developed with a Temple University Fox School of Business professor specialising in AI in Finance, for retail traders and finance students who need a risk-free way to learn and validate strategies.

- **OwlSpeaks GPT** — a custom RAG pipeline over live market data, so natural-language queries are grounded in current financial context with cited sources.
- **Screener and paper trading** — rule-based filters (P/E, RSI, volume, momentum, sector) with alerts and charting overlays, plus a paper-trading engine with trade journaling, P&L attribution, and drawdown analytics.

### Catalog Risk Auditor — `github/catalog-risk-auditor`

[Devpost](https://devpost.com/software/catalog-risk-auditor)
*Python 3.10+ · HumanStandard detection API · zero runtime dependencies*

**🏆 Winning project at the Philadelphia AI Agent Hackathon** (late September, 19 teams, per Technical.ly).

Audits a music catalog before acquisition: it scores every asset for AI generation, sorts the catalog into clean / contested / suspect using calibrated detection tiers, joins the result to reported revenue, and produces a risk memo with a recommended escrow figure.

- **Results:** suspect assets were 37.5% of the demonstration catalog by count but only 17.4% by revenue, producing a recommended escrow of $171,710 against a $720,000 asking price. It caught 6 of 6 AI tracks with zero human tracks wrongly flagged. 275 tests, 90% coverage, zero runtime dependencies.

### Schuylkill Sentinel

[Devpost](https://devpost.com/software/schuylkill-sentinel)
*Next.js 15 · TypeScript · Gemini · TimescaleDB (Tiger Data) · Leaflet · ElevenLabs*

**🏆 Hackathon-winning project, built for OwlHacks.**

Answers the one question a Philly rower actually asks — "Is the water OK today?" — with a live map of six riverfront spots, each scored 0–100 for combined-sewer-overflow and river risk after rain.

- Data comes from USGS gauges and Open-Meteo rainfall; a transparent, rule-based risk model scores each spot, and a Gemini agent ("Ask the Sentinel") calls the same tools and streams its reasoning trace live, with an ElevenLabs read-aloud option.
- **Results:** 48 tests covering each risk factor, band boundaries, and the agent route in every failure mode, with cached-fixture fallbacks so it never shows a blank screen.

## Core skills

**Agent governance and security:** Neurosymbolic policy enforcement, autoformalization, policy-as-code, trajectory scanning, monitor agents, human-in-the-loop (HITL), prompt-injection defenses, PII redaction, RBAC, audit trails, MCP servers and MCP Apps

**Agents, ML and RAG:** LangGraph, LangChain, GPT-4, Amazon Bedrock / AgentCore, NVIDIA Nemotron, Gemini / Vertex AI, Tavily, Qloo, RAG pipelines, vector databases, OpenAI embeddings, PyTorch, scikit-learn, SHAP, NLP, fine-tuning, text classification

**Languages and platforms:** Python, Rust, Java, C++, TypeScript, SQL · React, Svelte, Next.js, Spring Boot, Node.js, FastAPI · AWS (Lambda, ECS/EKS, Kinesis, EventBridge, Step Functions, SageMaker, Bedrock), GCP, Terraform, Docker, Kubernetes, Kafka, PostgreSQL, MongoDB, MySQL, Redis

## Education and certifications

- **M.S. Computer Science, Temple University**, Philadelphia, PA — Expected May 2027 · GPA 3.64/4.0 · Applied ML, interpretable AI, deep learning, neural network architectures, computer vision
- **B.Tech Computer Science Engineering, SMRIST**, Chennai, India — May 2019 · GPA 9.28/10 · Dean's List, Academic Excellence Award
- **Certifications:** AWS Solutions Architect – Associate (2024) · HashiCorp Terraform Associate (2024)
- **Recognition:** JPMorgan Chase internal Hackathon winner (2024) · Catalog Risk Auditor — winning project, Philadelphia AI Agent Hackathon · Schuylkill Sentinel — hackathon-winning project, OwlHacks · Global Code Warrior World Cup: Top 50 Global Final
- **Published:** "Sentimental Analysis Using GSM Technologies," IJARIIE (2018)

## Let's connect

- Email: [dashsoundarya12@gmail.com](mailto:dashsoundarya12@gmail.com)
- LinkedIn: linkedin.com/in/soundarya-dash
- Devpost: [devpost.com/dashsoundarya](https://devpost.com/dashsoundarya?ref_content=user-portfolio&ref_feature=portfolio&ref_medium=global-nav)
- This portfolio: [github.com/codergirl73/soundarya-dash-673](https://github.com/codergirl73/soundarya-dash-673)

Open to work on agentic AI, agent governance and security, and production ML systems.
