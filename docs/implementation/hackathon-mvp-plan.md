# Hackathon MVP Plan

## Direction

Build **Tiffin on top of Google AI Edge Gallery**. Do not rebuild the app from
scratch. Reuse the Gallery's on-device AI; add the Tiffin agent layer.

End-to-end target:

    shake  ->  voice in (Audio Scribe)  ->  on-device LLM  ->  summary via notification

## Locked MVP Choices

- Base: fork of Google AI Edge Gallery (Apache-2.0).
- Phone stack: the Gallery's existing Android app (Kotlin).
- On-device LLM: LiteRT via the Gallery's model management.
- Voice: the Gallery's **Audio Scribe** (on-device STT).
- Device control (later): the Gallery's **Mobile Actions** (FunctionGemma 270m).
- Skills (later): the Gallery's **Agent Skills** + MCP.
- Tiffin additions: daemon, shake trigger, proactive loop, notifications.

## Reuse vs Add

Reuse from the Gallery (do not rebuild):
- model download/management, LiteRT inference, Audio Scribe, Mobile Actions,
  Agent Skills, MCP, on-device privacy.

Add for Tiffin:
- a foreground-service **daemon** that runs in the background
- a **shake-to-wake** start/stop trigger (accelerometer)
- a **proactive agent loop** (sense -> wake -> act -> report)
- **notification** status + summary output
- (later) optional laptop pairing for heavier local processing

## First Workflow (MVP)

1. Daemon runs; ongoing notification shows "Idle - shake to start."
2. Shake -> wake -> invoke Audio Scribe to capture voice.
3. Send the transcript to the on-device LLM (LiteRT) for a short summary.
4. Show the summary as a notification (and in-app). Shake again to cancel.

A from-scratch prototype of this exact loop already exists in the separate
`sharp119/tiffin` repo (branch `feat/phone-shake-voice-llm`) and serves as the
reference; here we re-implement it by wiring into the Gallery instead.

## Acceptance Criteria

- Daemon runs with an ongoing notification.
- Shake starts/stops a session; state is visible in the notification.
- Voice is captured on-device (Audio Scribe).
- The on-device LLM produces a summary with no internet.
- The summary appears as a notification.
- Upstream Gallery app, `LICENSE`, and attribution remain intact.

## Out Of Scope (for now)

- Rebuilding any capability the Gallery already provides.
- Cloud anything; production connectors; the full laptop "brain."
- Acting across arbitrary apps (start with the loop above; expand via Mobile
  Actions / Agent Skills next).
