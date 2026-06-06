# Handoff

## Current Objective

Seed this Gallery fork with Tiffin's documentation, scope, and workflow so the
repo clearly becomes "Tiffin, built on Google AI Edge Gallery." (Docs/scope only
in this pass — no app code changed yet.)

## Locked Decisions

- Build Tiffin on top of Google AI Edge Gallery; do not rebuild from scratch.
- Reuse Gallery capabilities (LiteRT LLM, Audio Scribe, Mobile Actions, Agent
  Skills, MCP); add the Tiffin layer (daemon, shake trigger, proactive loop,
  notifications).
- Keep upstream intact (`LICENSE`, attribution, original README preserved under
  `docs/upstream/`).
- Phone-first, offline-first, privacy-first framing (carried from the original
  Tiffin scope).

## Done In This Pass

- Imported + adapted Tiffin docs/scope/workflow from the original `sharp119/tiffin`
  first-commit planning set, reframed for "built on the Gallery."
- Added `AGENTS.md`, `README.md` (Tiffin), `CLAUDE.md`, `docs/`, and
  `plans/hackathon-mvp/`.
- Preserved the original Gallery README at `docs/upstream/AI_EDGE_GALLERY_README.md`.

## Next Recommended Steps

1. Read the Gallery's `Android/` app + `DEVELOPMENT.md` to find where to hook in.
2. Locate the entry points for Audio Scribe (voice) and on-device LLM inference.
3. Add the Tiffin daemon + shake trigger as a new module/feature in the app.
4. Wire the MVP loop: shake -> Audio Scribe -> on-device LLM -> summary notification.
5. Port the reference loop from `sharp119/tiffin@feat/phone-shake-voice-llm`.

## Open Questions

- Cleanest place in the Gallery app to add a foreground-service daemon.
- Public/internal APIs for invoking Audio Scribe + the LLM from the daemon.
- Default model from the allowlist for the demo.

## Git State

This lane was created on branch `docs/tiffin-scope` (fork of Gallery `main`).
