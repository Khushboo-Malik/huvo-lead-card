# Call-to-Site-Visit Lead Card

A small prototype built for Huvo AI. It takes post-call webhook events from a voice agent talking to real-estate leads and turns each call into a lead card: budget, BHK, locality, timeline, site-visit slot and objections. It then scores the lead Hot, Warm or Cold and drafts a WhatsApp follow-up.

**Live demo:** https://khushboo-malik.github.io/huvo-lead-card/

## What it shows
- Idempotent webhook handling: a duplicate `call.completed` event (same `event_id`) is skipped instead of creating a second lead.
- Extraction that understands Hinglish ("kal shaam", "max 1.5 crore", "2 BHK") and turns it into structured fields.
- Lead scoring that explains its reasons, so a sales team can trust the score.

The extraction uses rules, so the demo runs in the browser with no API key. In production it would be an LLM call with structured output, with these rules kept as validators.

Everything is in a single `index.html` with no dependencies. The calls are mock data.

Built by Khushboo Malik. Not affiliated with Huvo AI.
