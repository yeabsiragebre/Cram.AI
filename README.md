<!--
  ═══════════════════════════════════════════════════════════════════════
  Cram AI — public launch README
  · Live demo: https://marvin-cram-ai.vercel.app
  · Source:     https://github.com/yeabsiragebre/Cram-ai
  ═══════════════════════════════════════════════════════════════════════
-->

<div align="center">

<img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 48 48'%3E%3Crect width='48' height='48' rx='12' fill='%2312110E'/%3E%3Cpath d='M36.26 13.71A16 16 0 1 0 36.26 34.29' fill='none' stroke='%23EFE9DD' stroke-width='5' stroke-linecap='round'/%3E%3Ccircle cx='40' cy='24' r='3.4' fill='%23B99AFF'/%3E%3C/svg%3E" width="96" height="96" alt="Cram AI logo">

# Cram AI

### Sit the exam before the exam.

**Cram AI turns your topics, lecture notes, and PDFs into a practice exam — generated in seconds, graded the moment you submit, and the concepts you keep missing become flashcards.**

Built by **Marvin AI Technologies** — building useful intelligence.

[![Python 3.13](https://img.shields.io/badge/python-3.13-3776AB.svg?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/downloads/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.110+-009688.svg?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![SQLAlchemy 2](https://img.shields.io/badge/SQLAlchemy-2.0+-DG8A4C.svg?style=for-the-badge&logo=sqlalchemy&logoColor=white)](https://www.sqlalchemy.org/)
[![Vercel](https://img.shields.io/badge/Vercel-ready-000000.svg?style=for-the-badge&logo=vercel&logoColor=white)](https://vercel.com/)
[![Docker](https://img.shields.io/badge/Docker-supported-2496ED.svg?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![PRs welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=for-the-badge)](https://github.com/yeabsiragebre/Cram-ai/pulls)

<br>

<a href="https://marvin-cram-ai.vercel.app">
  <img src="https://img.shields.io/badge/Live%20Demo-Try%20Cram%20AI-B99AFF?style=for-the-badge&logo=vercel" alt="Live demo">
</a>
<a href="https://github.com/yeabsiragebre/Cram-ai">
  <img src="https://img.shields.io/badge/GitHub-Source%20Code-181717?style=for-the-badge&logo=github" alt="GitHub source">
</a>
<a href="https://github.com/yeabsiragebre/Cram-ai/stargazers">
  <img src="https://img.shields.io/github/stars/yeabsiragebre/Cram-ai?style=for-the-badge" alt="GitHub stars">
</a>

<br>

**[✨ Features](#-features)** • **[How it works](#-how-it-works)** • **[Architecture](#-architecture)** • **[Quick start](#-quick-start)** • **[API](#-api-reference)** • **[Deploy](#-deployment)** • **[FAQ](#-faq)**

</div>

---

## 🔗 Live links

| Link | URL |
| --- | --- |
| **Source code** | <https://github.com/yeabsiragebre/Cram-ai> |
| **Live demo** | <https://marvin-cram-ai.vercel.app> |
| **Interactive API docs** (when running) | `GET /docs` — auto-generated Swagger UI |
| **Health check** | `GET /health` |

> 💡 Star the repository to follow development, and open an [issue](https://github.com/yeabsiragebre/Cram-ai/issues) with questions, bugs, or feature ideas.

---

## 📸 Preview

![Cram AI — practice exams generated from your notes, graded on submit](frontend/og-image.png)

A dark, calm, keyboard-first study app: sidebar navigation, command palette (`Ctrl K`), a quiz sheet with live grading, a draggable Cram Coach assistant, flashcards, a study heatmap, and a planner — all served by one FastAPI process.

---

## 📑 Table of contents

<details open>
<summary>Click to collapse</summary>

1. [About](#-about)
2. [Features](#-features)
3. [How it works](#-how-it-works)
4. [The generation pipeline](#-the-generation-pipeline)
5. [Architecture](#-architecture)
6. [Tech stack](#-tech-stack)
7. [Project structure](#-project-structure)
8. [Quick start](#-quick-start)
9. [Configuration reference](#-configuration-reference)
10. [API reference](#-api-reference)
11. [Testing](#-testing)
12. [Deployment](#-deployment)
13. [Security and privacy](#-security-and-privacy)
14. [Roadmap](#-roadmap)
15. [Contributing](#-contributing)
16. [FAQ](#-faq)
17. [License](#-license)
18. [Acknowledgments](#-acknowledgments)

</details>

---

## 🎯 About

**Cram AI** is an AI-powered exam preparation platform that generates practice papers from a student's own material — a topic, pasted notes, or a PDF — and grades every answer the moment it is submitted. An optional past-exam PDF teaches Cram the *style* of the real paper (question types, topic mix, difficulty profile, even the kind of thinking each question rewards), so generated practice feels like the genuine article.

### The problem

- **Generic study materials** don't match what will actually be on the exam.
- **Static question banks** become predictable — you end up memorizing answers, not concepts.
- **Manual test creation** is slow for educators and impossible for most students.
- **Slow feedback loops** mean mistakes are discovered days later, in the real exam.

### The solution

Cram AI closes the loop between studying and being tested:

- 🎯 **Generate** a practice paper from a topic or your course material in under a minute.
- 🪞 **Mirror a past exam** — match its question types, topics, difficulty, and cognitive style proportionally.
- ✅ **Grade live** — every answer is evaluated on submit with an explanation.
- 🧠 **Surface weak spots** — missed concepts are collected, ranked by frequency, and turned into drills and flashcards.
- 🤖 **Coach on demand** — Cram Bot gives hints during a quiz without revealing answers.

### What makes it different

| Most quiz generators | Cram AI |
| --- | --- |
| Random questions from a topic | Questions **proportionally matched** to a real past exam across four dimensions |
| Past exam used as a fact source (leakage risk) | Past exam used as **style reference only** — semantic, groundedness, and ambiguity gates reject leaked or ungrounded items |
| One-shot generation | **Quality-gated pipeline** with adaptive buffering, multi-round regeneration, and rejection feedback |
| Static score at the end | **Per-answer grading with explanations**, missing-concept extraction, and a persistent weak-spot list |
| Standalone quiz | Full study loop: quiz → weak spots → flashcards → planner → retry, with streaks and a 17-week activity heatmap |

---

## ✨ Features

### 🧠 AI question generation

- **From a topic** — type "Krebs cycle" or "eigenvalues", pick count (1–20), question types, and difficulty; questions are usually ready in under 30 seconds.
- **From your notes** — paste up to 100,000 characters of lecture notes or upload a course PDF (up to 10 MB). PDFs are parsed in memory and never written to disk.
- **Past-exam style matching** — optionally upload a past exam PDF. Cram analyzes its question-type mix, topic clusters, difficulty profile, and cognitive-type mix, then generates a *new* paper that mirrors those proportions without reusing its questions.
- **Five question formats** — multiple choice, true/false, matching, fill-in-the-blank, and short answer.
- **Streaming generation** — when a past exam is provided, progress streams over Server-Sent Events ("Cram is reading through your past exam…", "Cram is figuring out what question types appear most…", …) so the wait is visible, not silent.

### 🎓 The generation pipeline

- **Four-dimensional proportional targeting** — question *type*, *topic/facet*, *difficulty* (5-level LLM classification), and *cognitive type* (recall, comparison, cause-effect, application, interpretation, analysis) are each allocated with a floor-of-one plus largest-remainder algorithm.
- **Quality gates** — every generated question is checked in a single batched LLM pass for semantic similarity to the past exam, groundedness in your course material, and ambiguity (multiple defensible answers). Failures are rejected with a reason.
- **Adaptive buffering and regeneration** — when past-exam overlap is high, Cram requests extra questions up front; shortfalls trigger proportional regeneration with rejection feedback fed back into the prompt.
- **Anti-leakage by design** — the past exam is never used as a source of facts. Similarity, groundedness, and ambiguity checks run on every question before it reaches the student.

### 📝 Quiz experience

- **Full sheet or focus mode** — one question at a time or the whole paper, your choice.
- **Live grading** — each answer is graded on submit with a score, feedback, and an explanation.
- **Exam tools** — elapsed timer, flag-for-review, 50/50 lifeline where applicable, read-aloud, auto-advance in focus mode.
- **Keyboard-first** — `A`–`F` or `1`–`6` to pick an option, `Enter` to submit, `J`/`K` to navigate, `M` to flag, `V` for focus mode, `Ctrl K` for the command palette.
- **Finishing touches** — confetti on completion, soft sound effects (optional), and a resume banner so an in-progress quiz is never lost.

### 🔁 The learning loop

- **Weak spots** — concepts flagged on missed answers are collected and ranked by frequency. "Practice top spot" builds a new quiz focused on that concept.
- **Flashcards** — every attempt turns into a flippable deck (`Space` to flip); missed questions land here automatically.
- **History** — searchable, filterable (topic vs. document source), sortable attempts with a score trend chart, review of past answers, retakes, CSV/JSON export, and deletion.
- **Study planner** — tasks and exam dates on a calendar, with browser-notification reminders and an agenda view.
- **Study pulse** — streak counter, quizzes taken, average score, questions answered, a daily-goal ring, and a 17-week activity heatmap on the home screen.

### 🤖 Cram Bot (Cram Coach)

- A context-aware study assistant available as a full page and as a draggable, resizable widget inside quizzes.
- **Hint discipline** — before grading it explains concepts and nudges without revealing the answer; after grading it explains why each idea is right or wrong.
- Quick prompts (Hint, Explain, About Cram), streaming replies, and per-message stop generation.
- Selectable **Core AI model profile** in Settings — a fast default is included on the free plan; premium profiles require an active subscription.

### 👥 Accounts, plans, and administration

- **Google sign-in** with server-side sessions (httpOnly cookies) — no passwords stored.
- **Free plan** — 3 exam generations and 10 Cram Bot replies per UTC day, tracked with concurrency-safe quota reservations.
- **Subscriptions** — weekly ($2), monthly ($5), and yearly ($48, about $4/month) plans with country-aware indicative pricing; manual payment requests are reviewed and activated by an administrator.
- **Admin panel** — dashboard overview, user management with suspension, subscription grants and request review, quota limit configuration, usage analytics, system events, audit logs, and account-wide broadcast messages with threaded user replies.
- **Account messages** — admin notices, your replies, and error reports, with unread counts in the notification bell.

### 🎨 Craft

- Light and dark themes, five accent presets plus custom color, four text-size levels, reduce-motion and sound toggles.
- Command palette (`Ctrl K`), shortcuts cheat-sheet (`?`), "Surprise me" topic dice, recent-topic suggestions.
- Animated canvas intro (skippable, respects reduced motion), toasts, skeleton loaders, responsive layout with a mobile tab bar and resizable desktop sidebar.
- Open Graph share card and theme metadata for rich link previews.

---

## 🔄 How it works

```
┌──────────────┐     ┌────────────────────┐     ┌─────────────────┐
│  1. Choose   │     │  2. Shape the      │     │  3. Answer and  │
│    a source  │ ──▶ │     paper          │ ──▶ │    get graded   │
│  topic / PDF │     │  types, count,     │     │  live feedback  │
│  (+ past     │     │  difficulty, style │     │  + explanation  │
│   exam)      │     │  mirroring         │     │                 │
└──────────────┘     └────────────────────┘     └────────┬────────┘
                                                          │
                                                          ▼
                                              ┌─────────────────────┐
                                              │  4. Close the gaps  │
                                              │  weak spots → drills│
                                              │  → flashcards →     │
                                              │  planner → retry    │
                                              └─────────────────────┘
```

1. **Choose a source** — a specific topic, pasted notes, or a course-material PDF. Optionally add a past exam so Cram mirrors its phrasing and question mix.
2. **Shape the paper** — up to 20 questions across multiple choice, true/false, matching, fill-in-the-blank, and short answer, at the difficulty you need.
3. **Answer, get graded** — each answer is checked on submit, with an explanation and the concepts you missed.
4. **Close the gaps** — missed concepts land in Weak spots. Drill them, flip through flashcards, or retry only the questions you got wrong.

---

## ⚙️ The generation pipeline

When a past exam is provided, generation runs a four-dimensional matching pipeline (internally called **V3 proportional matching**):

```mermaid
flowchart TD
    A[Course material PDF or text] --> S[source_text]
    P[Past exam PDF or text] --> E[exam_style_text]
    E --> R[Regime detection<br/>MULTI_SUBJECT vs SINGLE_DOMAIN]
    E --> T[LLM: question-type discovery]
    E --> T2[LLM: topic / facet clustering]
    E --> D[LLM: difficulty classification<br/>5 levels]
    E --> C[Heuristic: cognitive-type mix<br/>recall → analysis]
    S --> G[Grounding corpus]
    R --> ALL[Proportional targets<br/>floor-of-1 + largest remainder]
    T --> ALL
    T2 --> ALL
    D --> ALL
    C --> ALL
    ALL --> GEN[Constrained generation<br/>adaptive buffer when overlap ≥ 40%]
    GEN --> Q[Quality gates<br/>similarity · groundedness · ambiguity]
    Q -->|reject| REG[Regeneration<br/>proportional shortfall + rejection feedback]
    Q -->|accept| OUT[Question paper]
    REG --> Q
    G --> Q
```

**Step by step:**

1. **Regime detection** — decides whether the past exam spans many subjects (topic clustering mode) or drills one domain (8 content facets such as properties, mechanisms, definitions).
2. **Analysis (4 batched LLM calls)** — question-type counts, topic clusters, a 5-level difficulty distribution, and a 6-category cognitive-type mix (Bloom-inspired: recall, comparison, cause-effect, application, interpretation, analysis). The cognitive classifier is heuristic and was validated at 100% agreement on a 20-question hand-labeled exam and 80% on a second set.
3. **Proportional allocation** — each dimension's distribution is converted into exact per-category counts using floor-of-one guarantees plus largest-remainder rounding, so a 70/30 MC/TF exam produces a 70/30 practice paper.
4. **Constrained generation** — the LLM receives concrete counts for all dimensions at once. When past-exam overlap is ≥ 40%, an adaptive buffer (up to 1.3×) requests extra questions up front to absorb expected rejections.
5. **Quality gates** — one batched LLM pass checks every question for (a) semantic similarity to the past exam, (b) groundedness in your course material, and (c) ambiguity. Rejected questions carry a reason.
6. **Regeneration** — shortfalls trigger additional rounds with the *same* proportional targets recomputed for the remaining count, and previous rejection reasons are injected into the prompt as negative constraints.

**Anti-leakage guarantee:** the past exam shapes *how* questions are asked, never *what* they ask about. Facts come only from your course material, and any item that is too similar, ungrounded, or ambiguous is rejected before you ever see it.

---

## 🏗️ Architecture

### System design

```mermaid
graph TB
    subgraph Client["Client (served by FastAPI)"]
        UI[Vanilla JS SPA<br/>index.html · app.js · style.css]
    end

    subgraph API["API layer — FastAPI"]
        AUTH[auth · Google OAuth + sessions]
        EXAMS[exams · generate / evaluate / attempts]
        DOCS[documents · PDF upload]
        STREAM[streaming · SSE generation]
        TUTOR[tutor · Cram Coach chat]
        PLANNER[planner · tasks and exams]
        SUBS[subscriptions · plans and requests]
        MSGS[messages · admin notices]
        USAGE[usage · quota status]
        ADMIN[admin · dashboard]
    end

    subgraph Services["Service layer"]
        AI[ai_service<br/>V3 proportional matching<br/>quality gates · evaluation]
        DOC[document_service<br/>in-memory PDF extraction]
        QUOTA[quota_service<br/>reservations · daily limits]
    end

    subgraph Data["Data layer"]
        ORM[SQLAlchemy 2 models]
        DB[(SQLite dev<br/>PostgreSQL prod)]
    end

    subgraph External["External"]
        LLM[Configurable OpenAI-compatible LLM endpoint]
        GOOGLE[Google OAuth 2.0]
    end

    UI --> AUTH & EXAMS & DOCS & STREAM & TUTOR & PLANNER & SUBS & MSGS & USAGE & ADMIN
    AUTH --> GOOGLE
    EXAMS --> AI
    STREAM --> AI
    TUTOR --> AI
    DOCS --> DOC
    EXAMS --> QUOTA
    STREAM --> QUOTA
    TUTOR --> QUOTA
    AI --> LLM
    AUTH & EXAMS & PLANNER & SUBS & MSGS & ADMIN & USAGE --> ORM
    ORM --> DB
```

### Layered responsibilities

| Layer | Location | Responsibility |
| --- | --- | --- |
| **API routes** | `backend/app/api/v1/routes/` | HTTP handling, Pydantic validation, quota reservation, auth via `Depends(require_user)` / `Depends(require_admin)` |
| **Services** | `backend/app/services/` | Business logic — AI generation and evaluation, PDF extraction, quota management |
| **Schemas** | `backend/app/schemas/` | Request/response DTOs |
| **Models** | `backend/app/models/` | SQLAlchemy ORM tables (users, sessions, attempts, entitlements, quotas, planner, messages, audit) |
| **Core** | `backend/app/core/` | Settings (`pydantic-settings`), database engine, security (Google ID-token verification, session tokens) |
| **Database utilities** | `backend/app/db/` | Out-of-band migrations and initialization |
| **Frontend** | `frontend/` | Static SPA served by FastAPI at `/` (assets under `/static`) |

### Database strategy

- **Local development:** SQLite by default (`sqlite:///./cram_ai.db`) — zero setup.
- **Production (Vercel):** PostgreSQL (e.g. Neon). The app uses the **pooled** URL (`DATABASE_URL_POOLED`) for request traffic and refuses to start on serverless platforms when the effective URL is SQLite, so account data can never appear to work while being silently lost.
- **Migrations are out-of-band:** `python -m backend.app.db.migrate` runs against the **direct** connection (`DATABASE_URL`) because DDL and advisory locks require a real session. The app itself never creates tables at import, startup, or request time — Vercel does not run migrations for you.
- Migrations are **additive only** (create missing tables, add missing columns), serialized with a PostgreSQL advisory lock, and safe to re-run.

---

## 🧱 Tech stack

| Layer | Technology | Purpose |
| --- | --- | --- |
| **Backend** | Python 3.13 · FastAPI | Async API, Pydantic validation, dependency injection |
| **AI** | OpenAI-compatible SDK → configurable LLM endpoint | Question generation, quality gates, answer evaluation, coaching |
| **Database** | SQLAlchemy 2.0 · SQLite (dev) · PostgreSQL/Neon (prod) | ORM, server-side sessions, attempts, quotas, subscriptions |
| **Auth** | Google OAuth 2.0 (Identity Services) + httpOnly session cookies | Passwordless sign-in, server-side sessions, suspension enforcement |
| **Documents** | pypdf | In-memory PDF text extraction with a typed error taxonomy |
| **Frontend** | Vanilla JS · CSS3 · SSE client | No build step, served statically by FastAPI |
| **Streaming** | Server-Sent Events | Real-time generation progress |
| **Deployment** | Vercel (Python function) · Docker | Serverless or containerized production |
| **Testing** | pytest · httpx | Unit and integration coverage |

---

## 📂 Project structure

```
Cram-ai/
├── main.py                        # Vercel serverless entrypoint (imports the FastAPI app)
├── vercel.json                    # Function config (maxDuration 300s)
├── Dockerfile                     # python:3.13-slim + uvicorn container
├── pyproject.toml / requirements.txt
├── .env.example                   # Every environment variable, documented
├── backend/
│   └── app/
│       ├── main.py                # App wiring, CORS, static frontend, SQLite guard
│       ├── api/v1/routes/
│       │   ├── auth.py            # Google login, profile, /auth/me, logout
│       │   ├── exams.py           # /generate, /evaluate, /attempts CRUD
│       │   ├── documents.py       # /upload (PDF → text, 10 MB, in-memory)
│       │   ├── streaming.py       # /generate-stream (SSE progress)
│       │   ├── tutor.py           # /tutor/chat (Cram Coach, model profiles)
│       │   ├── planner.py         # Study tasks and exam dates
│       │   ├── usage.py           # Quota status for the current user
│       │   ├── subscriptions.py   # Plans, requests, cancel/resume
│       │   ├── messages.py        # Account messages + admin broadcasts
│       │   └── admin.py           # Dashboard, users, limits, analytics, audit
│       ├── core/
│       │   ├── config.py          # pydantic-settings (all env vars)
│       │   ├── database.py        # Engine + session (pooled URL for traffic)
│       │   └── security.py        # Google ID-token verify, session tokens
│       ├── db/
│       │   ├── init_db.py         # Local bootstrap helper
│       │   └── migrate.py         # Out-of-band additive migrations (direct URL)
│       ├── models/                # user.py (10 tables) · exam_attempt.py
│       ├── schemas/               # auth.py · exam_attempt.py (Pydantic DTOs)
│       └── services/
│           ├── ai_service.py      # V3 proportional matching + quality gates + evaluation
│           ├── ai_service_streaming.py
│           ├── document_service.py# PDF extraction (corrupted/encrypted/empty/scanned errors)
│           └── quota_service.py   # Reservations, daily limits, limit events
├── frontend/
│   ├── index.html                 # SPA shell (auth, nav, all pages)
│   ├── app.js                     # Router, quiz engine, flashcards, planner, admin UI
│   ├── v3_upload_handler.js       # SSE client for streaming generation
│   ├── style.css                  # Design system (themes, accents, text scaling)
│   └── og-image.png               # Branded Open Graph share card
├── scripts/                       # Validation harnesses (leakage, proportions, regimes)
├── backend/tests/                 # pytest suite + integration tests
└── docs/                          # ARCHITECTURE.md · STREAMING_IMPLEMENTATION.md
```

---

## 🚀 Quick start

### Prerequisites

| Requirement | Version | Purpose |
| --- | --- | --- |
| **Python** | 3.13 | Runtime (pinned in `pyproject.toml` and `.python-version`) |
| **LLM API key** | — | Question generation, evaluation, and coaching (use credentials from your chosen LLM provider) |
| **Google OAuth client ID** | — | Sign-in ([Google Cloud Console](https://console.cloud.google.com/)) — web application type |
| **Git** | 2.0+ | Version control |

Optional: [Docker](https://www.docker.com/) for containerized runs, or a Neon/Postgres database for production-like local testing.

### 1. Clone and install

```bash
git clone https://github.com/yeabsiragebre/Cram-ai.git
cd Cram-ai

# Virtual environment
python -m venv .venv
# Windows PowerShell:  .venv\Scripts\Activate.ps1
source .venv/bin/activate

# Install dependencies (pick one)
pip install -r requirements.txt        # classic pip
# uv sync                              # or uv (uv.lock is committed)
# pip install -e .                     # or editable install
```

### 2. Configure environment

```bash
cp .env.example .env
```

Edit `.env` — at minimum set `LLM_API_KEY` and `GOOGLE_CLIENT_ID`:

```env
LLM_API_KEY=your_api_key_here
LLM_BASE_URL=https://your-openai-compatible-llm-endpoint/v1
LLM_MODEL=your-model-name

GOOGLE_CLIENT_ID=your_client_id.apps.googleusercontent.com
ADMIN_EMAIL=you@example.com            # optional: grants admin access

DATABASE_URL=sqlite:///./cram_ai.db    # local dev default
# SESSION_COOKIE_SECURE=true           # set for HTTPS deployments
# CORS_ORIGINS=https://your-domain.com
# PUBLIC_URL=https://your-domain.com   # for Open Graph share cards
```

### 3. Initialize the database and run

```bash
# Create tables (additive, idempotent; uses DATABASE_URL directly)
python -m backend.app.db.migrate

# Start the server
uvicorn backend.app.main:app --reload --host 127.0.0.1 --port 8000
```

### 4. Verify

- **App:** <http://localhost:8000> — sign in with Google, build a quiz from a topic.
- **Health:** <http://localhost:8000/health> → `{"status": "ok"}`
- **Interactive API docs:** <http://localhost:8000/docs> (Swagger UI) or `/redoc`

> The frontend is served by FastAPI itself — no separate frontend server or build step is needed.

### Docker alternative

```bash
docker build -t cram-ai .
docker run --rm -p 8000:8000 --env-file .env cram-ai
# open http://localhost:8000
```

---

## ⚙️ Configuration reference

All settings come from environment variables (`.env` supported locally via `pydantic-settings`).

| Variable | Default | Description |
| --- | --- | --- |
| `LLM_API_KEY` | — | **Required.** API key for the OpenAI-compatible LLM endpoint. |
| `LLM_BASE_URL` | `https://your-openai-compatible-llm-endpoint/v1` | LLM endpoint (any OpenAI-compatible API works). |
| `LLM_MODEL` | `your-model-name` | Model used for generation, evaluation, and coaching. |
| `GOOGLE_CLIENT_ID` | — | Google OAuth 2.0 web-client ID for sign-in. |
| `ADMIN_EMAIL` | empty | Verified Google email that receives administrator access. Empty disables admin. |
| `DATABASE_URL` | `sqlite:///./cram_ai.db` | **Direct** connection. Used by the migration command; request traffic only falls back to it when `DATABASE_URL_POOLED` is unset. |
| `DATABASE_URL_POOLED` | empty | **Pooled** connection (e.g. Neon `-pooler` endpoint) for normal request traffic on serverless. |
| `SESSION_COOKIE_NAME` | `cram_session` | Session cookie name. |
| `SESSION_COOKIE_MAX_DAYS` | `30` | Session lifetime in days. |
| `SESSION_COOKIE_SECURE` | `false` | Cookie `Secure` flag; auto-enabled behind HTTPS via `X-Forwarded-Proto`. |
| `CORS_ORIGINS` | local dev origins | Comma-separated allow-list. Never `*` together with credentialed cookies. |
| `PUBLIC_URL` | derived from request | Public origin for Open Graph share cards. |
| `OMNIROUTE_*` | — | Legacy provider config — disabled, kept only for rollback. |

Configuration priority: environment variables → `.env` file → defaults in `backend/app/core/config.py`.

---

## 🔌 API reference

Base URL: `http://localhost:8000` (or your deployment). Full interactive docs at `/docs` when the server runs.

### Authentication

Google OAuth 2.0 via Google Identity Services. The frontend exchanges a Google ID token for a server-side session:

1. `GET /api/v1/auth/config` — is Google sign-in enabled, client ID.
2. `POST /api/v1/auth/google` — body `{"credential": "<Google ID token>"}` → verifies the token server-side, creates/updates the user, sets an httpOnly session cookie, returns `{user}`.
3. `GET /api/v1/auth/me` — current session and profile.
4. `PATCH /api/v1/auth/profile` — update display name.
5. `POST /api/v1/auth/logout` — clears the session.

Suspended accounts are rejected with `403` on every authenticated request.

### Endpoints

| Method | Path | Auth | Description |
| --- | --- | --- | --- |
| `GET` | `/health` | — | Liveness probe |
| `POST` | `/api/v1/generate` | ✔ | Generate a question paper |
| `POST` | `/api/v1/generate-stream` | ✔ | Same, with SSE progress events |
| `POST` | `/api/v1/evaluate` | ✔ | Grade one answer with feedback |
| `POST` | `/api/v1/attempts` | ✔ | Save a completed attempt |
| `GET` | `/api/v1/attempts` | ✔ | List attempts (with trend data) |
| `DELETE` | `/api/v1/attempts/{id}` | ✔ | Delete an attempt |
| `POST` | `/api/v1/upload` | ✔ | Upload a PDF → extracted text (≤ 10 MB) |
| `POST` | `/api/v1/tutor/chat` | ✔ | Cram Coach reply (context-aware) |
| `GET/POST` | `/api/v1/planner/items` | ✔ | List / create planner items |
| `PATCH/DELETE` | `/api/v1/planner/items/{id}` | ✔ | Update / delete a planner item |
| `GET` | `/api/v1/usage/me` | ✔ | Today's quota usage and limits |
| `GET` | `/api/v1/subscriptions/plans` | ✔ | Available plans and prices |
| `POST` | `/api/v1/subscriptions/requests` | ✔ | Request a subscription (manual payment) |
| `GET` | `/api/v1/subscriptions/me` | ✔ | Current entitlement |
| `POST` | `/api/v1/subscriptions/cancel` · `/resume` | ✔ | Manage subscription |
| `DELETE` | `/api/v1/subscriptions/history` | ✔ | Clear subscription activity |
| `GET/PUT/POST/DELETE` | `/api/v1/messages/*` | ✔ | Account messages, unread counts, replies |
| `GET/POST` | `/api/v1/admin/*` | admin | Dashboard, users, limits, requests review, analytics, events, audit, broadcasts |

### Generate a paper

`POST /api/v1/generate`

```json
{
  "topic": "Cell respiration",
  "number_of_questions": 10,
  "source_text": "…extracted course material text (optional)…",
  "exam_style_text": "…past exam text (optional; style reference only)…",
  "question_types": ["multiple_choice", "true_false", "matching", "fill_in_the_blank", "short_answer"],
  "difficulty_levels": ["easy", "medium", "hard"]
}
```

**Response `200 OK`**

```json
{
  "questions": [
    {
      "question_text": "Which enzyme catalyses the first reaction of the Krebs cycle?",
      "question_type": "multiple_choice",
      "options": ["Aconitase", "Citrate synthase", "Isocitrate dehydrogenase"],
      "pairs": null,
      "correct_answer": "Citrate synthase",
      "explanation": "Citrate synthase joins acetyl-CoA and oxaloacetate to form citrate.",
      "difficulty": "medium",
      "topic": "Cell respiration"
    }
  ]
}
```

Question types: `multiple_choice`, `true_false`, `matching` (uses `pairs`), `fill_in_the_blank`, `short_answer`.

### Evaluate an answer

`POST /api/v1/evaluate` — body `{ "question": {…}, "student_answer": "…" }`

```json
{
  "correct": true,
  "score": 1.0,
  "maximum_score": 1.0,
  "confidence": 0.97,
  "feedback": "Exactly right — citrate synthase catalyzes the first step of the cycle.",
  "missing_concepts": []
}
```

Objective answers are compared with normalization (case/punctuation-insensitive, plus `|`-separated accepted variants); interpretive answers are graded semantically with a strict provider-side assessment.

### Streaming generation (SSE)

`POST /api/v1/generate-stream` — same body as `/generate`. Events arrive as `data: {json}\n\n`:

```
data: {"type": "progress", "message": "Cram is reading through your past exam...", "step": 1, "total": 5}
data: {"type": "progress", "message": "Cram is figuring out what question types appear most...", "step": 2, "total": 5}
data: {"type": "progress", "message": "Cram is discovering which topics matter most...", "step": 3, "total": 5}
data: {"type": "progress", "message": "Cram is checking question difficulty levels...", "step": 4, "total": 5}
data: {"type": "progress", "message": "Cram is crafting questions from your course material...", "step": 5, "total": 5}
data: {"type": "complete", "questions": [ … ]}
```

Topic-only generation skips analysis and streams a single step. The frontend (`frontend/v3_upload_handler.js`) picks the streaming endpoint automatically when a past exam is attached.

### Upload a PDF

`POST /api/v1/upload` — `multipart/form-data`, field `file` (PDF, ≤ 10 MB). Processed in memory, never persisted.

```json
{ "filename": "cell_biology_notes.pdf", "text": "…extracted text…", "char_count": 48210 }
```

Errors are typed and student-friendly: `400` non-PDF, `413` too large, `422` corrupted / encrypted / no text / scanned-image PDF (each with a `hint`).

### Cram Coach chat

`POST /api/v1/tutor/chat`

```json
{
  "page_context": "quiz",
  "model_profile": "cram",
  "topic": "Cell respiration",
  "question_number": 3,
  "total_questions": 10,
  "question": { "question_text": "…", "question_type": "multiple_choice", "options": ["…"], "answer_revealed": false },
  "messages": [{ "role": "user", "content": "Give me a small hint without revealing the answer." }]
}
```

→ `{ "reply": "…" }`. The coach sees page context, the live question, and whether it has been graded — ungraded questions get hints only, never answers. Premium `model_profile` values require an active subscription (`403 core_model_subscription_required`).

### Quotas and errors

- Chargeable operations (`generate`, `tutor`) take a **concurrency-safe reservation** first, so parallel requests cannot overspend a daily allowance. Free plan: **3 generations + 10 coach replies per UTC day**; Cram Coach is additionally capped at 30 requests/hour.
- Quota exceeded → `429` with a human-readable `detail`.
- AI provider failures map to `502` (invalid response), `503` (unavailable), `504` (timeout) with structured `{error, message, hint}` bodies.
- All failures are recorded in `ai_usage` and `system_events` for admin visibility.

---

## 🧪 Testing

```bash
# Run the suite
pytest

# Verbose / specific files
pytest -v backend/tests/test_answer_verification.py
pytest backend/tests/integration/test_live_scoring.py

# With coverage
pytest --cov=backend --cov-report=html
```

Included tests: answer verification, auth and admin guards, database architecture (pooled/direct split, SQLite-on-serverless refusal), markdown-fence stripping, and a live-scoring integration test. The `scripts/` directory holds the validation harnesses used during development — leakage regression, proportional-targeting checks, regime detection, difficulty and cognitive-type validation, and realistic end-to-end generation runs.

---

## 🚢 Deployment

### Vercel (production)

The repository is deployment-ready: `main.py` exports the FastAPI app as a Python Function, `vercel.json` raises the function timeout to 300 seconds (generation with a past exam can take around a minute), and the frontend is served from the same process.

1. **Create services** — GitHub repo → Vercel project; a managed PostgreSQL database (Neon or similar) with both a **direct** URL (migrations only) and a **pooled** URL (request traffic); a Google OAuth web client with the deployed domain as an authorized JavaScript origin; an API key from your chosen LLM provider.
2. **Set environment variables** for Production, Preview, and Development:

   | Variable | Value |
   | --- | --- |
   | `DATABASE_URL` | PostgreSQL **direct** URL — used only by the migration command |
   | `DATABASE_URL_POOLED` | PostgreSQL **pooled** URL — used by the application |
   | `LLM_API_KEY` / `LLM_BASE_URL` / `LLM_MODEL` | AI provider credentials |
   | `GOOGLE_CLIENT_ID` | Google OAuth web client ID |
   | `ADMIN_EMAIL` | Email to receive administrator privileges |
   | `CORS_ORIGINS` | Exact deployed origin(s), comma-separated |
   | `SESSION_COOKIE_SECURE` | `true` |
   | `PUBLIC_URL` | Public origin for Open Graph share cards |

3. **Run migrations before deploying** (Vercel never runs them for you):

   ```bash
   DATABASE_URL="postgresql://user:password@ep-xxxx-direct.neon.tech/neondb?sslmode=require" \
     python -m backend.app.db.migrate
   ```

   The command uses the direct URL only, is additive-only, serializes concurrent runs with an advisory lock, and refuses SQLite on Vercel production/preview deployments.

4. **Deploy and verify** — check `/health`, sign in with Google, then exercise generation, evaluation, history, and admin access against the production database.

> **Capacity note:** this repository has not been load-tested for hundreds of simultaneous active users. Real throughput depends on the Vercel plan, database connection limits (the production pool is deliberately small per instance), AI provider rate limits, and request mix. Run a staged load test before promising large concurrent numbers.

### Docker

```bash
docker build -t cram-ai .
docker run --rm -p 8000:8000 --env-file .env cram-ai
```

The container runs `uvicorn backend.app.main:app` on `PORT` (injected by Vercel-style environments; defaults to 8000).

---

## 🛡️ Security and privacy

- **Passwordless auth** — Google ID tokens are verified server-side; sessions are opaque tokens stored in the database and held by the browser in an httpOnly, SameSite=Lax cookie that gains `Secure` automatically behind HTTPS.
- **Least privilege** — admin routes require `Depends(require_admin)` matched against `ADMIN_EMAIL`; suspension revokes sessions immediately.
- **CORS done safely** — explicit origin allow-list; never `*` together with credentialed cookies.
- **Untrusted content discipline** — quiz text, pasted notes, and user profile names are treated as data, never instructions, inside AI prompts; Cram Coach's system prompt explicitly forbids revealing credentials, tokens, or hidden prompts.
- **Secrets stay server-side** — API keys live in environment variables only; the frontend never receives them.
- **Ephemeral documents** — PDFs are parsed in memory and never written to disk or stored in the database; only extracted text is used for generation.
- **No runtime schema changes** — the app never creates tables or migrates at import/startup/request time; migrations are additive, advisory-locked, and run out-of-band.
- **Serverless-safe** — SQLite is refused on Vercel production/preview so data cannot silently disappear between invocations.
- **Auditability** — admin actions write to `admin_audit_logs`; AI operations write to `ai_usage`; platform anomalies write to `system_events`.

---

## 🗺️ Roadmap

Ideas under consideration (contributions welcome):

- [ ] Spaced repetition scheduling for flashcards
- [ ] Adaptive difficulty that tracks a learner's ability over time
- [ ] Study groups and shared question banks
- [ ] Custom curriculum upload (syllabus-aware generation)
- [ ] Mobile apps (React Native / iOS / Android)
- [ ] Offline mode with cached question decks
- [ ] Multi-language interface (i18n)
- [ ] LMS integrations (Canvas, Moodle)
- [ ] Gamification — badges, streaks, leaderboards

---

## 🤝 Contributing

Cram AI is actively developed and contributions of every kind are welcome — code, tests, docs, design, bug reports, and ideas.

**Workflow:**

1. Fork the repository and create a feature branch (`feature/your-idea` or `fix/issue-description`).
2. Set up locally with the [Quick start](#-quick-start) guide.
3. Make focused changes; keep the layered architecture (routes → services → models) intact.
4. Add or update tests — every PR should keep `pytest` green.
5. Format with Black, add type hints, and write conventional commits (`feat:`, `fix:`, `docs:`, `test:`, `chore:`).
6. Open a pull request describing the change, the motivation, and how you tested it.

**Good first areas:** frontend polish and accessibility, more validation scripts, additional question-format coverage, test coverage for the streaming endpoint, documentation.

**Ground rules:** be respectful and constructive; review the code, not the person; treat user-generated content as untrusted in every AI prompt.

---

## ❓ FAQ

**Is Cram AI free?**
Yes — it is open source and self-hostable. The hosted free plan includes 3 exam generations and 10 Cram Bot replies per UTC day; you only pay your own LLM provider costs when self-hosting.

**What can I study with it?**
Anything. Generation is grounded in the material you provide — sciences, humanities, programming, languages, professional exams. Quality scales with the quality of the course material or past exam you upload.

**Does the past exam leak into the practice paper?**
No. The past exam is a *style reference only*. Similarity, groundedness, and ambiguity gates reject any generated item that copies, paraphrases, or cannot be traced to your course material.

**How long does generation take?**
Topic-only papers are usually ready in under 30 seconds. With a past exam attached, expect about a minute — and you watch the progress stream live.

**Can I self-host it?**
Absolutely. Docker is supported, and any OpenAI-compatible LLM endpoint can be configured via `LLM_BASE_URL` / `LLM_MODEL`.

**Does it work offline?**
Not currently — generation and grading call an LLM API. Offline cached decks are on the roadmap.

**Where is my data stored?**
In your own database (SQLite locally, PostgreSQL in production). Uploaded PDFs are processed in memory and never persisted.

**How accurate is the grading?**
Objective answers are checked deterministically with tolerant normalization; interpretive answers are graded semantically with a confidence score and explanation. As with any AI grader, review edge cases against your course material.

**Is there a mobile app?**
The web app is fully responsive (mobile tab bar, bottom navigation, touch targets). A native app is planned.

---

## 📄 License

Cram AI is released under the **[MIT License](https://opensource.org/licenses/MIT)**.

---

## 🙏 Acknowledgments

**Made by [Marvin AI Technologies](https://github.com/yeabsiragebre/Cram-ai)** — inspired by Marvin Minsky's pioneering work in AI, building intelligent software that makes complex tasks simpler, more efficient, and accessible. *Marvin AI Technologies. Building useful intelligence.*

Built with [FastAPI](https://fastapi.tiangolo.com/), [SQLAlchemy](https://www.sqlalchemy.org/), [Pydantic](https://docs.pydantic.dev/), [pypdf](https://pypdf.readthedocs.io/), your chosen OpenAI-compatible LLM provider, [Neon](https://neon.tech/), [Google Identity Services](https://developers.google.com/identity), and [Vercel](https://vercel.com/).

---

<div align="center">

**If Cram AI helps you study smarter, give it a star** ⭐

[![GitHub stars](https://img.shields.io/github/stars/yeabsiragebre/Cram-ai?style=social)](https://github.com/yeabsiragebre/Cram-ai/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/yeabsiragebre/Cram-ai?style=social)](https://github.com/yeabsiragebre/Cram-ai/network/members)
[![GitHub issues](https://img.shields.io/github/issues/yeabsiragebre/Cram-ai?style=social)](https://github.com/yeabsiragebre/Cram-ai/issues)

Source: [github.com/yeabsiragebre/Cram-ai](https://github.com/yeabsiragebre/Cram-ai)

*Sit the exam before the exam.*

</div>
