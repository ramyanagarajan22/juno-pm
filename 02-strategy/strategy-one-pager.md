# AI Strategy One-Pager - Juno Event AI Assistant

## 1. Problem & Workflow

The Problem: Prospective attendees researching an event often have questions before they register about relevant sessions, pricing, or whether the event fits their needs but had no fast way to get answers. They'd either call support (slow, costly) or, more often, simply abandon registration without ever asking.

Prevention: "Event AI Assistant" explicitly prevents attendees from abandoning registration due to an unanswered pre-registration question. By giving instant, accurate answers about sessions, pricing, and relevance at the exact moment someone is deciding whether to sign up, it removes the silent friction that was costing us registrations.

## 2. Target Metrics

Cycle time: My top KPI is registration conversion rate,  how many people who start signing up actually finish. Right now, 43% of people drop off partway through, so only 57% complete registration. Goal: cut drop-off to 30%, so conversion rises to about 70%. We can measure this within 30 days of launch, every event cycle.

Leadership proof: This is the number leadership won't want us to stop tracking. If it goes up, it directly proves the agent is answering the questions that were making people give up — and it's tied straight to revenue (completed registrations), not just clicks or usage. We'll also watch two supporting signals — sessions added to agenda and fewer support tickets — but conversion rate is the one number that proves this is working.

## 3. Autonomy Level

Choice: Copilot. The agent answers attendee questions, gives session recommendations, and can take actions like adding a session to an agenda but only after the user explicitly clicks to confirm. If the agent can't confidently answer a question, it routes the attendee to a human rather than guessing.

Explicitly avoiding: Agent. We are not letting the system take actions on a user's behalf without in-the-moment confirmation — e.g., no auto-adding sessions based on inferred interest, no auto-registering, no silent changes to an attendee's agenda. A wrong guess baked into a paying attendee's schedule erodes trust in a way a wrong FAQ answer doesn't so every action stays one click away from the user, never fully autonomous.

## 4. Data & Model Approach

Chosen Approach: Ground (RAG). The agent retrieves answers from our live, event-specific data sessions, speakers, capacity, pricing — before responding, so every answer reflects the actual state of that specific event, even as details change up until (and during) the event itself.

Explicitly avoiding: Buy (LLM). We're not letting the agent answer from general model knowledge alone. With many events running simultaneously and details (like session capacity) changing daily or even hour-by-hour during the event, an ungrounded answer could easily be plausible-sounding but wrong  confidently telling someone a session is open when it's actually full. That risk is unacceptable on a branded, trust-sensitive surface. (We're also ruling out fine-tuning for the same underlying reason: our event data is too dynamic to bake into model weights without constant retraining.)

## 5. Risks & Mitigations

Risk: During a live event, session data (especially capacity) can change within minutes — a session fills up, gets moved, or is cancelled. If the agent's retrieved data lags even slightly behind reality, it can confidently tell an attendee a session is available, and the attendee then one-click adds it to their agenda — baking a wrong, capacity-limited session into their real schedule. By the time they discover the error, they've missed the session they actually wanted, with no room left to fix it.

Mitigation: Enforce a strict data freshness threshold (e.g., capacity data no older than X minutes) directly in the retrieval layer. If the agent can't confirm data is fresh enough, it does not state availability as fact — instead it shows a "confirm availability" prompt or routes the user to the live registration page before allowing the one-click add.

## 6. V1 Scope

In scope (v1): Pre-registration support only — answering general event FAQs, recommending sessions/activities, and helping attendees register and add sessions to their agenda (via one-click, always user-confirmed).

Out (1): No autonomous actions. The agent will never auto-register an attendee or auto-add sessions to their agenda without an explicit click consistent with the Copilot boundary.

Out (2): No during/post-event support. The agent won't handle live-event questions (e.g., "what's happening right now"), session summaries, or on-demand content recommendations in v1. For those, it will point attendees to the relevant page (e.g., on-demand library, live schedule) rather than attempt to answer directly — keeping v1 scoped to the pre-registration problem.
