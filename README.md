# Tiffin — built on Google AI Edge Gallery

> This repository is a **fork of [Google AI Edge Gallery](https://github.com/google-ai-edge/gallery)** (Apache-2.0).
> We are building **Tiffin** on top of it. The original Gallery app, code, and
> `LICENSE` are kept intact; the original Gallery README is preserved at
> [`docs/upstream/AI_EDGE_GALLERY_README.md`](docs/upstream/AI_EDGE_GALLERY_README.md).

## What is Tiffin?

Tiffin is a **private, offline-first AI agent that lives on your phone.** The phone
is the doer: it senses, wakes on demand, and acts on the device. A laptop, when
nearby, is an optional local "brain" for heavier work. **Nothing goes to the cloud.**

We are **not building the app from scratch.** Google AI Edge Gallery already gives
us the hard parts, on-device and offline:

- **On-device LLM + LiteRT** and model management
- **Audio Scribe** — on-device speech-to-text
- **Mobile Actions** — offline device control (FunctionGemma 270m)
- **Agent Skills** + **MCP** — extensible tools
- **100% on-device privacy**

Tiffin adds the **agent workflow** on top of these:

- an always-on **daemon** (foreground service)
- a **shake-to-wake** trigger (proactive, never always-listening)
- a **proactive agent loop** (sense → wake → act → report)
- **notification-based** status and results

## Current MVP target

The first end-to-end loop (carried over from the Tiffin prototype):

    shake  ->  voice in (Audio Scribe)  ->  on-device LLM  ->  summary via notification

…then grow toward acting on the phone using Mobile Actions + Agent Skills.

## Where to start (source of truth)

1. [`AGENTS.md`](AGENTS.md) — how to work in this repo + project identity
2. [`docs/project/PROJECT_GUIDE.md`](docs/project/PROJECT_GUIDE.md) — durable project map
3. [`docs/architecture/core-architecture.md`](docs/architecture/core-architecture.md) — how Tiffin sits on the Gallery
4. [`docs/implementation/hackathon-mvp-plan.md`](docs/implementation/hackathon-mvp-plan.md) — current scope + feature list
5. [`docs/product/tiffin-narrative.md`](docs/product/tiffin-narrative.md) — the product story
6. [`plans/hackathon-mvp/HANDOFF.md`](plans/hackathon-mvp/HANDOFF.md) — current work state

To build the underlying app, see the upstream [`DEVELOPMENT.md`](DEVELOPMENT.md).

## Attribution & license

Built on [Google AI Edge Gallery](https://github.com/google-ai-edge/gallery),
licensed under the Apache License 2.0. This fork remains under Apache-2.0 — see
[`LICENSE`](LICENSE). Tiffin-specific docs and code are contributed under the same license.
