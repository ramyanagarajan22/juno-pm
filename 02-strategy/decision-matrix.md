# AI Solution Decision Matrix · Juno

## The decision

Deciding whether to build an in-house registration agent, leverage off-the-shelf LLM APIs with RAG, or fine-tune a custom model to answer attendee questions and guide session bookings for Connect 2026.

## Options scored

| Option | Cost | Speed | Control | Moat | Risk | Score |
|---|---|---|---|---|---|---|
| Build | 2 | 2 | 4 | 3 | 2 | 2.6 |
| Buy / API | 4 | 5 | 4 | 2 | 5 | 4.0 |
| Fine-tune | 1 | 1 | 3 | 4 | 2 | 2.2 |

## Recommendation

Buy / API. Leveraging off-the-shelf LLM APIs with RAG allows us to deploy the registration copilot immediately for Connect 2026 with minimal engineering overhead. Because session capacities and schedules update constantly, grounding via RAG provides real-time data freshness without the prohibitive cost, latency, or retraining overhead of fine-tuning or custom model development.
