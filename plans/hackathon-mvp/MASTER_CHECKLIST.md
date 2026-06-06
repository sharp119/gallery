# Master Checklist

## Docs And Scope (this pass)

- [x] Fork of Google AI Edge Gallery identified as the base.
- [x] Import + adapt Tiffin docs/scope/workflow from the original first commit.
- [x] Add AGENTS.md, README (Tiffin), architecture, implementation, narrative.
- [x] Preserve upstream README + keep `LICENSE`/app intact.
- [x] Log the "build on the Gallery" decision.

## Tiffin Layer (next)

- [ ] Locate hook points in the Gallery Android app.
- [ ] Add a foreground-service daemon.
- [ ] Add a shake-to-wake trigger (accelerometer).
- [ ] Invoke Audio Scribe for on-device voice input.
- [ ] Invoke the on-device LLM (LiteRT) for the summary.
- [ ] Post the summary as a notification; show state in the ongoing notification.
- [ ] Port the reference loop from `sharp119/tiffin@feat/phone-shake-voice-llm`.

## Demo Proof

- [ ] Daemon runs with an ongoing notification.
- [ ] Shake starts/stops a session.
- [ ] Voice captured on-device.
- [ ] On-device LLM summary with no internet.
- [ ] Summary shown as a notification.
