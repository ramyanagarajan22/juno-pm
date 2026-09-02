# Prototype · Juno

## Prototype link

https://claude.ai/public/artifacts/82e108b9-83ad-4a51-8125-118345156668

## What it demonstrates

Proves an embedded AI registration copilot can guide an attendee from session inquiry to lead capture (First Name, Last Name, Email, Company) and one-click agenda booking directly on an event registration landing page.

## Debrief

- **What worked:**
- The conversational chat drawer rendered smoothly over the landing page. It correctly enforced gated session booking (requiring attendee registration before booking) and dynamically presented interactive session cards with live capacity badges and explicit action buttons.

- **What broke / felt like a toy:**
- The session data and registration confirmation are hardcoded UI mocks rather than live dynamic database records. The chat state resets on page refresh, and it cannot yet query real-time backend seat availability APIs.

- **What I'd change next pass:**
- Connect a dynamic backend database (or vector search index) to enable real-time RAG context retrieval for session schedules, enforce strict data freshness thresholds for seat capacity, and add persistent user session storage.
