# AGENTS.md

Universal entry point for AI agents and contributors working on **Tiffin**.

Do not rely on chat history. Resume from repo files.

## Project Identity

This repository is a fork of **Google AI Edge Gallery** (Apache-2.0). We are
building **Tiffin** on top of it.

- Tiffin = a private, offline-first phone agent.
- phone = sense organ and doer; laptop = optional local heavy-lift; **no cloud**.
- We **build on the Gallery, we do not rebuild it**: reuse its on-device LLM
  (LiteRT), Audio Scribe (voice), Mobile Actions (device control), Agent Skills,
  and MCP. Add the Tiffin layer (daemon, shake trigger, proactive loop,
  notifications) on top.

## Start Every Session

1. Run `git status --short --branch`.
2. Read `README.md`.
3. Read `docs/project/PROJECT_GUIDE.md`.
4. Read `plans/hackathon-mvp/HANDOFF.md`.
5. If architecture/product is involved, read:
   - `docs/architecture/core-architecture.md`
   - `docs/implementation/hackathon-mvp-plan.md`
   - `docs/product/tiffin-narrative.md`
6. State what you learned before editing.

## Source Of Truth Hierarchy

1. `AGENTS.md` — operating rules
2. `docs/project/PROJECT_GUIDE.md` — durable repo context
3. `docs/architecture/core-architecture.md` — how Tiffin sits on the Gallery
4. `docs/product/tiffin-narrative.md` — product story
5. `docs/implementation/hackathon-mvp-plan.md` — current build scope
6. `plans/hackathon-mvp/HANDOFF.md` — current work state
7. Chat history only as a hint, never as authority.

## Build-On-Gallery Rules

- Prefer reusing a Gallery capability over writing a new one. If voice, LLM,
  device control, or skills already exist in the Gallery, wire into them.
- Keep upstream intact: do **not** modify `LICENSE`; keep Google's attribution;
  keep the original Gallery README at `docs/upstream/AI_EDGE_GALLERY_README.md`.
- Keep Tiffin changes additive and clearly marked so we can still pull upstream.

## Editing Rules

- Phone-first framing is mandatory. The laptop is support, not the hero.
- Preserve offline-first and privacy-first language.
- Do not invent benchmark numbers, prototype status, or working integrations.
- Keep mock/demo data clearly labeled.

## Git Rules

- Work on feature branches; do not force-push or rewrite shared history.
- Do not reset/checkout/delete user changes without permission.
- Keep commits focused.

## Session Close Criteria

- Update relevant docs + `plans/hackathon-mvp/HANDOFF.md`.
- Log major decisions in `plans/hackathon-mvp/DECISION_LOG.md`.
- Report git status and any dirty files.
