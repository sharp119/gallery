# Decision Log

## Build & Run The Original App First, Then Plan In Phases

Decision:
Before writing any Tiffin code, first get the unmodified Google AI Edge Gallery
app building and running on a device. Only after that, plan the Tiffin additions
as explicit phases, then build them.

Rationale:
A known-good baseline de-risks everything. We confirm the toolchain and that the
Gallery's on-device features (LLM, Audio Scribe, Mobile Actions) actually work on
our device before changing anything. Planning after the base runs keeps scope honest.

Consequences:
- Phase 0 = build & run the base (current task).
- Phase 1 = plan Tiffin in detail (write phase docs).
- Phase 2+ = build the Tiffin layer.

Follow-up:
- Record the working build steps + issues in
  `plans/hackathon-mvp/phases/PHASE-00_BUILD_AND_RUN_BASE.md`.

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

## Keep Tiffin's Original Scope And Workflow

Decision:
Carry over Tiffin's first-commit scope and workflow (phone-first, offline-first,
privacy-first; the shake -> voice -> LLM -> notification MVP) and adapt it to the
"built on the Gallery" approach.

Consequences:
- Docs and plans here mirror the original Tiffin planning set, adapted.
