---
title: "Point of View: The Intent Spec"
type: point-of-view
author: Damian Drewulski
date: 2026-09-13
status: ready to publish
tags: [pov, ai-delivery, vibe-coding, handoff, okr-6]
---

# Point of View: The Intent Spec

## Thesis

- The Intent Spec is a temporary, LLM-generated bridge — not a heavy PRD or technical ADR — designed to hand off vibe-coded gut decisions to engineering before being purposefully discarded.

## Why It Matters Now

- Vibe-coding bypasses the traditional cross-functional negotiation where constraints and goals are usually documented.
- Without a capture mechanism, the "why" and the "what not to do" behind the code disappear the moment the chat window closes.

## The Bet

- We do not need a bloated, traditional spec. We need a mandatory, automated questionnaire that synthesizes exactly four things from the AI session:
  1. **The Goal & Manifesto** — so it is clear exactly what is being built.
  2. **Hard Constraints** — e.g. mandatory UI frameworks, rules against storing personal data.
  3. **Deferred Elements** — features explicitly rejected, such as a hamburger menu or pagination.
  4. **Sample & Test Data** — to ground the engineering starting point.
- Once engineering takes over, it **promotes the durable items — the hard constraints and the key rejections — into permanent ADRs, and discards the rest.** The Intent Spec is the feeder for the durable record, then it is gone.

## Strongest Objection

- **Objection:** Spec rot. Who maintains this living document when reality hits and the code changes?
- **Response:** No one. It cannot rot because it does not live. It is a transient handover artifact, and whatever deserves to persist has already been promoted into ADRs by the receiving engineers. What is left has no reason to survive.

## How It Gets Made

- The Intent Spec is not written by hand. The AI session itself is prompted, at handover, to emit the four fields from the conversation it already holds — the goal, the constraints it was told to honour, the options it was told to drop, and the data it used. Synthesis is the model's job; the human reviews and signs off.

## The Ask

- Adopt this 4-field Intent Spec as the mandatory quality gate for handing over all AI-prototyped MVPs.
- Judge the handover on the spec, not on the vibe-coded snapshot alone: the product idea includes the turns, bumps, and rejected paths from the AI conversation, and those travel with the code exactly once — into the Intent Spec, then into the ADRs that outlive it.
