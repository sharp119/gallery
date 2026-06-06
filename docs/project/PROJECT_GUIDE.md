# Project Guide

## Purpose

Tiffin is a private, offline-first phone agent. This repository is a **fork of
Google AI Edge Gallery** that we are turning into Tiffin by adding an agent
workflow on top of the Gallery's on-device AI stack.

The phone is the sense organ and doer; the laptop helps with heavier processing
when nearby. Nothing leaves the device.

## Why build on the Gallery

The Gallery already provides, on-device and offline:
- On-device LLM execution via **LiteRT** + model management / allowlist.
- **Audio Scribe** — on-device speech-to-text.
- **Mobile Actions** — offline device control (FunctionGemma 270m).
- **Agent Skills** + **MCP** — extensible tools.
- **100% on-device privacy**.

Rebuilding these from scratch would waste the hackathon. Tiffin reuses them and
adds: a daemon, a shake trigger, a proactive agent loop, and notification I/O.

## Stack And Runtime

- Android app: the Gallery's existing Kotlin app (under `Android/`).
- On-device models: LiteRT via the Gallery's model management (`model_allowlist.json`).
- Tiffin layer (to add): foreground-service daemon, shake trigger, proactive loop,
  notifications — wired to Audio Scribe + on-device LLM + Mobile Actions.

## Repository Map

Upstream (Google AI Edge Gallery — keep intact):
- `Android/` — the Android app
- `mcp/`, `skills/`, `model_allowlist.json`, `model_allowlists/`
- `LICENSE`, `DEVELOPMENT.md`, `CONTRIBUTING.md`, and the upstream guides
- `docs/upstream/AI_EDGE_GALLERY_README.md` — preserved original README

Tiffin (added):
- `README.md` — Tiffin overview for this fork
- `AGENTS.md` — operating rules
- `docs/architecture/core-architecture.md`
- `docs/implementation/hackathon-mvp-plan.md`
- `docs/product/tiffin-narrative.md`
- `plans/hackathon-mvp/` — active planning lane

## Entry Points

- Agents/contributors: start at `AGENTS.md`.
- Product reviewers: `README.md` then `docs/product/tiffin-narrative.md`.
- Architecture: `docs/architecture/core-architecture.md`.
- Current status: `plans/hackathon-mvp/HANDOFF.md`.
- Build the app: upstream `DEVELOPMENT.md`.

## Maintenance Rules

- Reuse Gallery capabilities before writing new ones.
- Keep upstream intact (LICENSE, attribution, original README preserved).
- Keep Tiffin changes additive and clearly marked.
- Update `plans/hackathon-mvp/HANDOFF.md` and `DECISION_LOG.md` after meaningful work.
