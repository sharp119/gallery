# Phase 2+ — Tiffin Layer (skeleton — detail in Phase 1)

> This is a placeholder. The real, detailed phases are written during Phase 1,
> AFTER the base app runs. Do not start this work until Phase 0 is done.

## Intended Scope

Add the Tiffin agent layer on top of the Gallery:

- Foreground-service **daemon**.
- **Shake-to-wake** trigger (accelerometer), start/stop.
- **Proactive loop**: sense -> wake -> act -> report (no typed prompt).
- **Notification** status + summary output.
- First loop: shake -> Audio Scribe (voice) -> on-device LLM -> summary notification.
- Later: optional laptop pairing for heavier local processing.

## Reference

A from-scratch prototype of the first loop exists in
`sharp119/tiffin@feat/phone-shake-voice-llm` — port it by wiring into the Gallery
instead of rebuilding.
