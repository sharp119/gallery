# Decision Log

## Build Tiffin On Google AI Edge Gallery (not from scratch)

Decision:
Build Tiffin on top of a fork of Google AI Edge Gallery instead of building the
Android app from scratch.

Rationale:
The Gallery already provides, on-device and offline, the hard parts Tiffin needs:
LiteRT LLM execution + model management, Audio Scribe (speech-to-text), Mobile
Actions (device control via FunctionGemma 270m), Agent Skills, and MCP. Rebuilding
these in a hackathon would waste time and be worse.

Alternatives considered:
- Build a native Android app from scratch (the original Tiffin plan; a working
  prototype of the shake -> voice -> LLM -> notification loop exists in
  `sharp119/tiffin@feat/phone-shake-voice-llm`).
- Build an independent on-device agent framework.

Consequences:
- This repo becomes "Tiffin, built on the Gallery." Upstream code, `LICENSE`, and
  attribution are kept intact; Tiffin changes are additive.
- The from-scratch prototype becomes a reference, not the main line.

Follow-up:
- Wire the Tiffin daemon + shake trigger into the Gallery app and reuse Audio
  Scribe + the on-device LLM for the MVP loop.

## Keep Tiffin's Original Scope And Workflow

Decision:
Carry over Tiffin's first-commit scope and workflow (phone-first, offline-first,
privacy-first; the shake -> voice -> LLM -> notification MVP) and adapt it to the
"built on the Gallery" approach.

Consequences:
- Docs and plans here mirror the original Tiffin planning set, adapted.
