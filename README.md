<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=1a1a2e&height=180&section=header&text=Mariyala%20Abhinav%20Teja&fontSize=36&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=AI%2FML%20Engineer%20%7C%20Full-Stack%20Developer%20%7C%20Applied%20Research&descAlignY=55&descSize=16" width="100%"/>

[![Profile Views](https://komarev.com/ghpvc/?username=abhinavteja123&color=1a1a2e&style=flat-square&label=PROFILE+VIEWS)](https://github.com/abhinavteja123)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/abhinav-teja-40855a293/)
[![Portfolio](https://img.shields.io/badge/Portfolio-Visit-333333?style=flat-square&logo=firefox&logoColor=white)](https://abhinavteja.vercel.app)
[![Email](https://img.shields.io/badge/Email-Contact-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:mariyalaabhinavteja@gmail.com)

</div>

## About

Final-year B.Tech CSE (AI & ML) student at SRM University AP (CGPA 8.13), building production-grade AI systems across static analysis, agentic pipelines, RAG, and computer vision. AWS Certified Cloud Practitioner. Currently interning at Vextra AI and Aurocoders, working on LLM-powered automation and full-stack AI products.

Focus areas: multi-agent systems, retrieval-augmented generation, developer security tooling, and applied deep learning — with an emphasis on shipping things that are measured, not just demoed.

---

## Experience

**Vextra AI** — AI Intern *(Remote, India)*
Full-stack production modules and AI-accelerated development workflows.

**Aurocoders** — Software Developer / AI Automation *(Remote, India)*
Built an LLM-powered cold-outreach automation pipeline (Node.js/Express + Gemini) with a real-time review dashboard; technical SEO audits and Python data-validation pipelines processing 1,000+ records per batch.

**Kokonda Dental Hospital** — Full Stack Developer Intern *(Hyderabad, India)*
React.js + Firebase features improving page load by 25%; admin dashboards for patient and appointment management.

---

## Featured Projects

### CodeMore — Static Analysis Built for AI Coding Agents

Open-source SAST tool with a report schema designed to be read and acted on by the same AI agent that wrote the bug, not a human at a dashboard.

- 64 native rules across 6 packs (core-security, core-quality, vibe-auth, vibe-frontend, vibe-secrets, vibe-supabase) plus 8 opt-in external adapters (Ruff, Biome, Bandit, Gitleaks, clippy, golangci-lint, npm-audit, pip-audit)
- ~90% BLOCKER true-positive rate in the latest audit across 7 real codebases, including a live OpenAI key and Firebase Admin SDK credentials caught behind `.gitignore`
- One schema-stable `codemore-report.json`, verified byte-identical across four surfaces: CLI, MCP server (6 tools, for Cursor/Claude Code/Codex), VS Code extension, and a GitHub Action
- Agentic fix loop (plan → generate → validate → retry, max 3 attempts) with a validator harness that never silently keeps a failing patch
- 128-fixture regression corpus (one TP/FP pair per rule) enforced in CI; rules gated through an experimental → beta → stable lifecycle by measured false-positive rate

`TypeScript` `Node.js` `MCP` `GitHub Actions` `VS Code Extension API`

[View Repository](https://github.com/abhinavteja123/codemore) · [npm](https://www.npmjs.com/package/codemore)

---

### SVIES — Smart Vehicle Identification & Enforcement System

7-layer AI traffic enforcement pipeline for Indian roads, trained on an NVIDIA V100. Submitted as an IEEE/Springer conference paper.

- Custom YOLOv8 models: 97.7% mAP@50 license plate detection, 74.4% mAP@50 helmet detection (trained across ~14,947 images from 10 merged datasets)
- Custom CRNN OCR (CNN + BiLSTM + CTC decoder): 99.8% character accuracy, 98.1% full-plate accuracy on 50k synthetic Indian plates, with EasyOCR/Tesseract/Groq-Llama fallback and IS 10731 grammar-constrained correction across all 36 state codes
- Fake-plate forensics: 5-check system (type mismatch, CMVR color-code violation, font anomaly, duplicate/clone detection, state mismatch) cross-referenced against VAHAN/PUCC/insurance records
- Geofenced enforcement across 14+ zones (Shapely polygon operations) with repeat-offender escalation scoring and auto-generated PDF court summons
- 12-page React dashboard with Firebase role-based auth (ADMIN/POLICE/RTO/VIEWER) and an active-learning loop for feedback-driven model retraining with versioned hot-swap deployment

`Python` `YOLOv8` `PyTorch` `FastAPI` `React` `Firebase` `Supabase`

[View Repository](https://github.com/abhinavteja123/SVIES)

---

### Ledger Oracle — Fact-Checked Refund Verification Agent

Built for the Razorpay AI Buildathon 2026. A bounded investigation agent gathers evidence on a refund claim; a deterministic policy engine — not the LLM — makes the pass/block/escalate call.

- Core design split: the agent selects tools and gathers evidence, but the verdict is arithmetic over that evidence, so every decision is reproducible and auditable by hand
- Held-out evaluation (108 claims): 100% precision and recall on blocking fraudulent claims, zero false accusations of honest customers, ~95% escalation precision
- Adversarial hardening: prompt-injection and homoglyph-disguise corpus run through the real pipeline with `unsafe_pass_count` as a headline CI metric, evidence-binding fix to stop tool-argument tampering, and a deterministic replay harness proving no LLM sits in the decision path
- Multi-provider LLM fallback (Groq to Gemini) with graceful degradation — every provider failure escalates safely rather than crashing
- Found and fixed a live Supabase RLS misconfiguration that left the production ledger writable by any anon key holder

`Python` `FastAPI` `Groq` `Gemini` `Supabase` `pytest`

[View Repository](https://github.com/abhinavteja123)

---

### SENTINEL-AI — Autonomous Incident Management System

8-agent SRE swarm that detects, analyzes, and remediates production incidents, with a human-in-the-loop gate for high-severity actions.

- Pipeline: LogWatcher to IncidentDetector to RiskClassifier to Planner to Approval to Executor, with Memory and Chat agents running alongside
- LOW/MEDIUM incidents auto-remediate; HIGH/CRITICAL incidents require human approval with modify/reject options before any action executes
- Multi-channel alerting: Twilio WhatsApp and Gmail SMTP, plus a real-time WebSocket dashboard showing live agent activity
- Conversational chat agent (Google ADK + Gemini) for querying incident history and remediation reasoning in natural language

`Python` `FastAPI` `Google Gemini` `WebSocket` `Twilio` `React`

[View Repository](https://github.com/abhinavteja123/SENTINEL_AI)

---

### ResolveIT AI — RAG-Powered IT Runbook Assistant

IT support assistant that answers only from indexed runbooks, with a confidence gate that refuses to answer rather than fabricate a citation.

- Retrieval pipeline: HyDE query expansion to hybrid search (FAISS dense vectors + BM25) to cross-encoder re-ranking (BAAI/bge-reranker-base) to confidence gate to Gemini generation
- 6 configurable answer modes (fast, standard, deep, eli5, expert, dryrun) tuning retrieval depth and response voice
- Streaming, token-by-token answers over Server-Sent Events, every step carrying an inline citation back to the source runbook
- Full-stack deployment: Firebase Google Auth, Supabase-backed audit logging, per-user runbook uploads, feedback loop, and admin analytics for runbook health and knowledge-gap detection

`Python` `FastAPI` `FAISS` `Gemini` `React` `Firebase` `Supabase` `Docker`

[View Repository](https://github.com/abhinavteja123/resolveit-ai)

---

### ProofSnap — Cryptographic Deepfake Verification (HackSRM 7.0 Winner)

React Native app that gives every photo an unforgeable trust score at the moment of capture.

- 7-step pipeline: SHA-256 hash to Ed25519 device signature to on-chain anchor (DataHaven Testnet, Chain 55931, custom Solidity `MediaProof.sol`) to AI deepfake detection to weighted Trust Score to watermarking to Supabase sync
- Any pixel-level change — screenshot, crop, filter, re-compression — breaks the hash chain and is mathematically detectable
- Offline-first: local SQLite cache and hardware-backed secure key storage, full functionality without network access
- 3-mode verification (transaction hash, file hash, image re-hash) plus a batch gallery scanner for tamper detection across an entire device

`TypeScript` `React Native` `Expo` `Solidity` `ethers.js` `Supabase`

[View Project](https://devfolio.co/projects/proofsnap-ef2b)

---

## Tech Stack

**Languages**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)

**AI / ML**
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21F?style=flat-square&logo=huggingface&logoColor=black)
![YOLOv8](https://img.shields.io/badge/YOLOv8-111F68?style=flat-square)
![FAISS](https://img.shields.io/badge/FAISS-00758F?style=flat-square)
![Google Gemini](https://img.shields.io/badge/Google_Gemini-4285F4?style=flat-square&logo=google&logoColor=white)
![Groq](https://img.shields.io/badge/Groq-F55036?style=flat-square)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square)

**Backend**
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)

**Frontend**
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=next.js&logoColor=white)
![React Native](https://img.shields.io/badge/React_Native-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)

**Cloud / Infrastructure**
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazon-aws&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white)
![Render](https://img.shields.io/badge/Render-46E3B7?style=flat-square&logo=render&logoColor=white)

**Tools**
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![VS Code](https://img.shields.io/badge/VS_Code-007ACC?style=flat-square&logo=visual-studio-code&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)

---

## Certifications

- **AWS Certified Cloud Practitioner** — 2025
- **JNCIA-Junos** — In Progress
- The Joy of Python — NPTEL
- Web & Mobile UI/UX Design (Figma) — Udemy

---

## Education

**SRM University AP** — B.Tech Computer Science and Engineering (AI & ML) · 2023–2027 · CGPA 8.13

- HackSRM 7.0 — Winner, Sponsor Track (ProofSnap)

---

## GitHub Stats

<div align="center">
<img height="165" src="https://github-readme-stats.vercel.app/api?username=abhinavteja123&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true&bg_color=0D1117"/>
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=abhinavteja123&layout=compact&langs_count=8&theme=tokyonight&hide_border=true&bg_color=0D1117"/>
</div>

<div align="center">
<img src="https://github-readme-streak-stats.herokuapp.com/?user=abhinavteja123&theme=tokyonight&hide_border=true&background=0D1117&stroke=1a1a2e&ring=1a1a2e&fire=FF6B6B&currStreakLabel=1a1a2e" alt="GitHub Streak"/>
</div>

<div align="center">
<img src="https://github-readme-activity-graph.vercel.app/graph?username=abhinavteja123&theme=tokyo-night&hide_border=true&area=true&bg_color=0D1117&color=1a1a2e&line=1a1a2e&point=FF6B6B" alt="Contribution Graph" width="100%"/>
</div>

---

<div align="center">

**Hyderabad, Telangana, India · SRM University AP**

[![Email](https://img.shields.io/badge/Email-mariyalaabhinavteja@gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:mariyalaabhinavteja@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/abhinav-teja-40855a293/)
[![Portfolio](https://img.shields.io/badge/Portfolio-Visit-333333?style=flat-square&logo=firefox&logoColor=white)](https://abhinavteja.vercel.app)

<img src="https://capsule-render.vercel.app/api?type=waving&color=1a1a2e&height=100&section=footer" width="100%"/>

</div>
