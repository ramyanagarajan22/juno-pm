# AI Solution Decision Matrix · Juno

## The decision

Deciding whether to build an in-house triage tool, leverage off-the-shelf LLM APIs with RAG, or fine-tune a custom model to automate incoming request triage across Slack, Asana, and support channels.

## Options scored

| Option | Cost | Speed | Control | Moat | Risk | Score |
|---|---|---|---|---|---|---|
| Build | 2 | 2 | 4 | 3 | 2 | 2.6 |
| Buy / API | 4 | 5 | 4 | 2 | 5 | 4.0 |
| Fine-tune | 1 | 1 | 3 | 4 | 2 | 2.2 |

## Recommendation

Buy / API. Leveraging off-the-shelf LLM APIs with RAG allows us to deploy the PM triage copilot immediately with minimal upfront engineering costs and extremely low risk. It provides high control over prompt guardrails while solving the weekly 5-hour triage bottleneck without the heavy maintenance, time, or expense required to build custom infrastructure or fine-tune models from scratch.
