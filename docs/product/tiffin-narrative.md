# Tiffin Narrative

## Product Frame

Tiffin is an offline-first AI worker that lives on your phone. It senses, wakes
when needed, and acts on the device — privately, with nothing sent to the cloud.

We build Tiffin **on Google AI Edge Gallery**, which already runs powerful models
fully on-device. Tiffin turns that capable "model sandbox" into a proactive agent.

## One-Line Pitch

Tiffin turns your phone into a private, offline AI worker — built on Google AI Edge
Gallery — that wakes on a shake, listens, and acts on the device.

## Why The Name

A tiffin is a packed box carried through the day. The phone carries Tiffin and acts
on it throughout the day; the laptop, when nearby, helps pack heavier work.

## Roles

- Phone: the star — senses, wakes, acts, offline.
- Laptop: optional heavy-lift when nearby.
- Gallery: the on-device AI engine Tiffin is built on.

## What Tiffin Does

- Runs quietly as a daemon; wakes on a shake (never always-listening).
- Listens via the Gallery's on-device voice (Audio Scribe).
- Thinks with an on-device LLM (LiteRT) — no internet.
- Replies and reports through notifications.
- (Next) acts on the phone via Mobile Actions and Agent Skills.

## Differentiation

Most assistants are cloud chatbots that wait for prompts. Tiffin is phone-first,
offline, and **proactive**: it wakes itself and acts on the device, keeping data
local. Building on the Gallery means real on-device AI from day one, not a
from-scratch toy.

## Product Guardrails

- Do not call it a personal AI OS.
- Do not frame the laptop as the main brain.
- Do not sound cloud-dependent.
- Do not claim integrations are built until they are.
- Keep demo/mock data clearly labeled.
