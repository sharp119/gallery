# Core Architecture

## Working Frame

Tiffin is built **on top of Google AI Edge Gallery**. The Gallery is our on-device
AI substrate; Tiffin is the agent workflow layered over it.

## Architecture Thesis

The phone is the primary agent because it is closest to the user's life and can act
on the device. The laptop is a temporary heavy-lift processor when nearby. Nothing
goes to the cloud.

For the hackathon, implement only as far as needed to prove one end-to-end loop:
**shake -> voice -> on-device LLM -> summary notification**, reusing Gallery
components wherever possible.

## What the Gallery already gives us (reuse)

- **On-device LLM + LiteRT** and model management — Tiffin's "brain" on the phone.
- **Audio Scribe** — on-device speech-to-text — Tiffin's voice input.
- **Mobile Actions** (FunctionGemma 270m) — offline device control — Tiffin's "hands."
- **Agent Skills + MCP** — reusable tools — Tiffin's skill system.
- **100% on-device privacy** — matches Tiffin's privacy-first stance.

## What Tiffin adds (the layer)

1. **Daemon** — a foreground service that keeps the agent alive in the background.
2. **Triggers** — shake-to-wake (then time / notification triggers later);
   proactive, never always-listening.
3. **Proactive agent loop** — sense -> wake -> act -> report, without a typed prompt.
4. **Notification I/O** — an ongoing status notification + a result/summary notification.
5. **Optional laptop brain** — heavier local processing when paired; still no cloud.

## Core Roles

### Phone: Sense Organ And Doer
- Wakes explicitly (shake) or on schedule; never passively listens.
- Uses the Gallery's on-device LLM for reasoning and Audio Scribe for voice.
- Acts on the device through Mobile Actions / Agent Skills.
- Shows status and results via notifications and the app.

### Laptop: Optional Heavy-Lift
- When nearby, does deeper processing and hands results back to the phone.
- Never required for the phone to work.

## Core Data Objects (conceptual)

- `Trigger` — what woke the agent (shake / time / event).
- `Session` — one wake-to-result run.
- `Skill` — a reusable task (Gallery Agent Skill / MCP tool).
- `Result` — what the agent produced (e.g. a summary) and how it was shown.

## Open Questions For MVP

- Which Gallery entry points to hook the daemon + trigger into.
- How to invoke Audio Scribe + the on-device LLM programmatically from the daemon.
- Shake sensitivity and background/battery behavior on the demo device.
- Which model from the allowlist to default to for the demo.
