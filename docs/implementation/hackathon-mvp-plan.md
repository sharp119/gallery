# Hackathon MVP Plan

## Direction

Build **Tiffin on top of Google AI Edge Gallery**. Do not rebuild the app from
scratch. We move in phases:

1. **Get the original Gallery app building and running first** (Phase 0).
2. **Then plan** exactly what Tiffin adds, in detailed phases (Phase 1).
3. **Then build the Tiffin layer** (Phase 2+), reusing the Gallery's on-device AI.

Eventual end-to-end target (built only after the base runs and planning is done):

    shake  ->  voice in (Audio Scribe)  ->  on-device LLM  ->  summary via notification

## Phase 0 — Build & Run The Original App (current task)

Goal: a clean, working build of the **unmodified** Gallery on a real device, so we
have a known-good baseline before adding anything.

- Build the app per the upstream `DEVELOPMENT.md`.
- Install and run it on a physical Android device.
- Confirm the base on-device features work: model download/run (LiteRT), Audio
  Scribe (voice), Mobile Actions, Agent Skills.
- Record the working toolchain (Android Studio / Gradle / JDK) and any fixes.

Done when: the stock Gallery app runs on-device and its core features work. No
Tiffin code added yet.

## Phase 1 — Plan Tiffin (after Phase 0)

Goal: decide what Tiffin adds and break it into detailed phases.

- List the Tiffin features we want (daemon, shake trigger, proactive loop,
  notifications; later: laptop pairing, more triggers).
- Map each to a Gallery capability to reuse vs new code to add.
- Find the hook points in the Gallery `Android/` app.
- Write detailed phase docs under `plans/hackathon-mvp/phases/`.

Done when: there is an agreed, written phase plan for the Tiffin layer.

## Phase 2+ — Tiffin Layer (to be planned in Phase 1)

Skeleton (to be detailed): add a foreground-service daemon, a shake-to-wake
trigger, a proactive loop, and notification I/O; wire shake -> Audio Scribe ->
on-device LLM -> summary notification. A from-scratch reference prototype of this
loop exists in `sharp119/tiffin@feat/phone-shake-voice-llm`.

## Reuse vs Add (guiding rule)

Reuse from the Gallery: model management, LiteRT inference, Audio Scribe, Mobile
Actions, Agent Skills, MCP, on-device privacy.
Add for Tiffin (later phases): daemon, shake trigger, proactive loop, notifications.

## Out Of Scope (for now)

- Rebuilding any capability the Gallery already provides.
- Cloud anything; production connectors; the full laptop "brain."
- Writing Tiffin feature code before Phase 0 (the base build) is done.
