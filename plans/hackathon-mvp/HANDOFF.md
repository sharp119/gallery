# Handoff

## Current Objective

**Phase 0 — build and run the ORIGINAL Google AI Edge Gallery app**, unmodified,
on a real device. Establish a known-good baseline before any Tiffin code. Only
after that do we plan the Tiffin phases (Phase 1).

## Locked Decisions

- Build Tiffin on top of Google AI Edge Gallery; do not rebuild from scratch.
- Work in phases: (0) build & run the base, (1) plan Tiffin in detail, (2+) build
  the Tiffin layer.
- Reuse Gallery capabilities (LiteRT LLM, Audio Scribe, Mobile Actions, Agent
  Skills, MCP); add the Tiffin layer later.
- Keep upstream intact (`LICENSE`, attribution, original README under
  `docs/upstream/`).
- Phone-first, offline-first, privacy-first.

## Done So Far

- Reframed this Gallery fork as "Tiffin, built on the Gallery": added `AGENTS.md`,
  Tiffin `README.md`, `docs/`, and `plans/hackathon-mvp/` (branch `docs/tiffin-scope`).
- Set the phased approach: build & run the base first, then plan.

## Next Steps (Phase 0)

1. Follow upstream `DEVELOPMENT.md` to build the app.
2. Install and run the unmodified app on a physical Android device.
3. Confirm core features work (model run, Audio Scribe, Mobile Actions).
4. Record the working toolchain + any issues in
   `plans/hackathon-mvp/phases/PHASE-00_BUILD_AND_RUN_BASE.md`.
5. When the base runs, move to Phase 1 (planning).

## Open Questions

- Build toolchain versions that work cleanly for this Gallery version.
- Which device(s) we will demo on.

## Git State

This lane is on branch `docs/tiffin-scope` (fork of Gallery `main`).
