# Master Checklist

## Phase 0 — Build & Run The Original App (current)

- [ ] Read upstream `DEVELOPMENT.md`; set up toolchain (Android Studio / JDK / Gradle).
- [ ] Build the unmodified Gallery app.
- [ ] Install + run it on a physical Android device.
- [ ] Confirm: download/run a model (LiteRT).
- [ ] Confirm: Audio Scribe (voice) works.
- [ ] Confirm: Mobile Actions works.
- [ ] Record working toolchain + issues in `phases/PHASE-00_BUILD_AND_RUN_BASE.md`.

## Phase 1 — Plan Tiffin (after base runs)

- [ ] List the Tiffin features we want.
- [ ] Map each to "reuse Gallery capability" vs "new code."
- [ ] Find hook points in the Gallery `Android/` app.
- [ ] Write detailed phase docs under `plans/hackathon-mvp/phases/`.

## Phase 2+ — Tiffin Layer (to be planned in Phase 1)

- [ ] Daemon (foreground service).
- [ ] Shake-to-wake trigger.
- [ ] Voice in via Audio Scribe.
- [ ] On-device LLM summary (LiteRT).
- [ ] Summary + status notifications.
- [ ] Port reference loop from `sharp119/tiffin@feat/phone-shake-voice-llm`.

## Docs (done)

- [x] Reframe repo as Tiffin built on the Gallery.
- [x] Phased approach recorded (build first, then plan).
- [x] Upstream preserved (`LICENSE`, attribution, original README).
