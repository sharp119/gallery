# Hackathon MVP Lane

## Objective

Turn this Google AI Edge Gallery fork into **Tiffin**: a private, offline-first,
proactive phone agent built on the Gallery's on-device AI.

## Locked Scope

- Base: fork of Google AI Edge Gallery (Apache-2.0).
- Reuse: LiteRT LLM, Audio Scribe, Mobile Actions, Agent Skills, MCP.
- Add: daemon, shake trigger, proactive loop, notifications.
- First loop: shake -> voice -> on-device LLM -> summary notification.

## Source Of Truth

- `docs/implementation/hackathon-mvp-plan.md`
- `docs/architecture/core-architecture.md`
- `docs/product/tiffin-narrative.md`
- `plans/hackathon-mvp/HANDOFF.md`

## Next Step

Hook the Tiffin daemon + shake trigger into the Gallery Android app and wire the
MVP loop, reusing Audio Scribe + the on-device LLM.
