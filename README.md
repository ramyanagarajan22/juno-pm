# Juno Event AI Assistant

> Juno Event AI Assistant eliminates event page drop-off by embedding directly on landing pages to guide prospective attendees through inline session discovery, real-time seat availability checks, and gated 1-click registration.

_Ramya Nagarajan - ai-product-management-aug17-26-weeknights_

Repo: https://github.com/ramyanagarajan22/juno-pm

This repo is my final project for the AI Product Management Certification — **Juno Event AI Assistant**. Each module’s artefact lives in its own folder; this README is the dashboard and the pitch.

---

## Module artefacts

### M1 · Prompting
- **System prompt** — [`01-prompting/system-prompt.md`](01-prompting/system-prompt.md)
- **Prototype** — [https://your-build-tool/share/your-juno-prototype](https://claude.ai/public/artifacts/82e108b9-83ad-4a51-8125-118345156668)

### M2 · Strategy
- **Decision matrix** — [`02-strategy/decision-matrix.md`](02-strategy/decision-matrix.md)
- **AI Strategy one-pager** — [`02-strategy/strategy-one-pager.md`](02-strategy/strategy-one-pager.md)

### M3 · RAG / AI PRD
- **AI PRD** — [`03-harness-prd/prd.md`](03-harness-prd/prd.md)

### M4 · AI-Native UX
- **AI user flow** — [`04-ai-ux/user-flow.md`](04-ai-ux/user-flow.md)
- **Trust-gap mitigations** — [`04-ai-ux/trust-gaps.md`](04-ai-ux/trust-gaps.md)

### M5 · Agentic Workflows
- **Agent Workflow Spec (AWSpec)** — [`05-agentic-workflows/awspec.md`](05-agentic-workflows/awspec.md)
- **Agent Control Panel** — [`05-agentic-workflows/agent-control-panel.md`](05-agentic-workflows/agent-control-panel.md)

### M6 · Evals &amp; Guardrails
- **Eval stack** — [`06-evals/eval-stack.md`](06-evals/eval-stack.md)
- **Human evaluation rubric** — [`06-evals/human-rubric.md`](06-evals/human-rubric.md)

---

## PM Execution Plan

### Where Juno is today
V1 Core Scope: Pre-registration copilot deployed on the Connect 2026 page.
Current Capabilities: RAG-grounded session search across 5 event tracks, real-time seat availability badges, inline lead capture (First Name, Last Name, Email, Company), and gated 1-click agenda booking cards.
Guardrails Enforced: Strict copilot boundaries that prevent un-gated auto-bookings or ungrounded availability claims.

### What ships next (next 2 sprints)
Sprint 1 (Data Freshness & Fallbacks): Implement automated fallback to "Check Live Availability" status cards whenever RAG latency or database freshness checks exceed threshold safety limits.
Sprint 2 (Multi-Session Routing & Smart Recommendations): Add multi-session bulk agenda booking, track-exhaustion alternative recommendations, and direct hand-off triggers for human support leads.

### What I watch (dashboards)
Primary Conversion Metrics: Overall registration conversion rate (target: raise from 60% to >75%) and drop-off rate inside the chat drawer (target: <25%).
Efficiency & Engagement: Average time-to-register (target: <60 seconds) and total sessions added per registered attendee agenda.
Eval & Quality Signals: Daily active/passive feedback scores (target: >85% thumbs-up, <10% regenerate rate) and nightly automated Golden-Set accuracy (>92%).

### Red lines (what blocks shipping)
0% PII Leakage: Any exposure of personal lead data immediately auto-blocks release.
0 Critical Safety Fails: Zero tolerance for any "1" score on Safety/Refusal during human evals (e.g., executing booking without explicit user button click).
Grounding Violations: <100% pass rate on citation/grounding assertions against live event session DB blocks deployment.

### Governance
Compliance & Safety: Enforces strict lead-capture gating before session booking; zero auto-booking permissions granted to the AI model.
Reliability: CI/CD automated Golden-Set checks run on every PR with nightly cron evaluations; weekly human eval scoring by 2 graders + PM tiebreak on a 50-run stratified sample.
Reputation: Automatic circuit breaker routes users to human support whenever model confidence drops or citation checks fail.

---

## Build Insights

- **Friction point.** RAG context latency during high-concurrency registration periods created potential race conditions between cached seat capacity numbers and real-time database inventory.
- **Key learning.** Enforcing explicit copilot boundaries (requiring user button clicks and inline forms) prevents costly autonomous errors while building higher user trust than full automation.
- **Aha moment.** Moving lead capture directly inside the interactive chat drawer cut time-to-register under 60 seconds and instantly eliminated the primary cause of landing page bounce rates.

## Repo structure

```
juno-pm/
├── README.md                          ← this dashboard + pitch
├── 01-prompting/
│   ├── system-prompt.md               ← M1: Juno's system prompt
│   └── lovable-prototype.md           ← M1: prototype link + debrief
├── 02-strategy/
│   ├── decision-matrix.md             ← M2: build / buy / fine-tune / partner call
│   └── strategy-one-pager.md          ← M2: AI strategy one-pager
├── 03-rag-prd/
│   └── prd.md                         ← M3: AI PRD with retrieval requirements
├── 04-ai-ux/
│   ├── user-flow.md                   ← M4: AI-native user flow
│   └── trust-gaps.md                  ← M4: trust-gap mitigations
├── 05-agentic-workflows/
│   ├── awspec.md                      ← M5: Agent Workflow Spec
│   └── agent-control-panel.md         ← M5: Agent Control Panel
└── 06-evals/
    ├── eval-stack.md                  ← M6: layered eval stack
    └── human-rubric.md                ← M6: human evaluation rubric
```

---

_Certification submission — AI Product Management Certification._
