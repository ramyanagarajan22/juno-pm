# AI Strategy One-Pager - Juno Event AI Assistant

## 1. Problem & Workflow

The Problem: Prospective attendees abandon registration when redirected away from event details into lengthy multi-step checkout forms, or when overwhelmed trying to manually filter through 50+ sessions across 5 tracks to assess relevance. This friction causes over 40% bounce rates on the event page and high drop-off midway through the registration flow.

Prevention: "Event AI Assistant" embeds directly on the event landing page to eliminate funnel drop-off. By offering instant session recommendations and gathering lead capture details (First Name, Last Name, Email, Company) directly inside a floating chat drawer, it gets attendees registered and scheduled in a single conversational interaction.

## 2. Target Metrics

Cycle time: My top KPI is registration conversion rate. Right now, over 40% of users bounce or drop off mid-flow. Goal: reduce drop-off to under 25% (raising conversion to 75%+) while reducing average time-to-register from minutes of manual browsing to under 60 seconds in-chat. We can measure this within 30 days of launch across active event marketing cycles.

Leadership proof: Conversion rate directly links the AI assistant to top-line revenue and completed registrations. Supporting signals include total sessions added to agendas, lead form completion rate inside chat, and a reduction in pre-registration support tickets.

## 3. Autonomy Level

Choice: Copilot. The assistant answers questions, captures registration inputs, and surfaces interactive session cards. Actions like finalizing registration or booking a session into an agenda require explicit user button clicks. If confidence or data freshness is low, it routes the user to a human agent.

Explicitly avoiding: Autonomous Agent & Ungated Booking. We do not permit autonomous actions (no auto-registering, no auto-adding sessions based on inferred interest). Furthermore, the assistant enforces a strict gate: no attendee can book a session without first completing registration details.

## 4. Data & Model Approach

Chosen Approach: Buy / API + Grounded Knowledge (RAG). We leverage off-the-shelf LLM APIs combined with a dynamic RAG pipeline. RAG retrieves live session schedules, speaker bios, pricing tiers, and real-time room capacity to keep answers 100% grounded and up to date.

Explicitly avoiding: Ungrounded LLMs & Custom Fine-Tuning. We are not relying on general model knowledge alone (which leads to hallucinated seat availability) nor fine-tuning a custom model. Because event schedules and capacity change constantly up to and during the event, fine-tuning carries prohibitive retraining costs and latency.

## 5. Risks & Mitigations

Risk: During peak registration, session seat capacity updates rapidly. If retrieved RAG context lags behind live seat inventory, the assistant might display "Seats Available" for a session that just filled up.

Mitigation: Enforce strict data freshness thresholds directly in the retrieval pipeline. If capacity data cannot be verified within the freshness window, the card falls back to a "Check Live Availability" status, prompting a real-time inventory check before permitting a 1-click booking.

## 6. V1 Scope

In scope (v1): Pre-registration support on the Connect 2026 page—answering session/pricing FAQs, inline lead capture (Name, Email, Company), gated 1-click agenda booking, and smart recommendation rotation across 5 event tracks.

Out (1): No direct landing-page bookings. Clicking "Add to agenda" on page cards opens the Juno drawer and surfaces the session in chat to enforce the registration gate, ensuring Juno remains the single point of actual booking.

Out (2): No during/post-event support. Live-event navigation, session summaries, or post-event video access are out of scope for V1, keeping the focus entirely on solving pre-registration bounce rates.
