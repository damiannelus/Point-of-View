---
title: "Beyond Vibe Coding: The Operating Model for Production-Grade AI"
type: point-of-view
author: Damian Drewulski
date: 2026-09-10
status: draft — language-corrected; pending altitude + one metric pass before publishing
tags: [pov, ai-delivery, ai-first, governance, okr-1, okr-6]
---

# Beyond Vibe Coding: The Operating Model for Production-Grade AI

The enterprise portfolio landscape is defined by a large, expensive graveyard of fragile pilots, and the vibe-code era has intensified it. Across industries, organizations are accumulating prototypes that look impressive in a boardroom demo but break the moment they touch a legacy codebase or a real production environment.

As a technology leader, I watch this cycle repeat. An operations expert, entrenched in their domain for years, gets a strong idea for how to automate a process. They assume they know exactly what the user needs without ever asking them — a classic manifestation of the "I am the user" fallacy. In the past this cognitive bias was dangerous, but the barrier to entry for software development kept it somewhat in check. The generative AI era has fundamentally lowered that barrier. It has never been easier to skip the critical product-discovery phase and jump straight into piling up features by blindly following the assistant's *"do you want me to…"* prompts.

A stream of ideas will not give you a solid spine for growing a product.

Through my work leading AI delivery and automation architecture, I have developed a three-pillar methodology to bridge this gap. It grounds guesswork in determinism, converts top-down mandates into developer pull, and turns endless meetings into rapid, validated prototypes. Here is how we build the architecture of reality.

## 1. The Brownfield Context Builder: determinism over guesswork

Once an initiative is validated, the reality of the enterprise environment sets in. We are rarely building on a pristine greenfield; we are building on top of decades of legacy code, tangled import graphs, and intricate dependencies.

The prevailing industry trend is to take a massive codebase, throw it into an LLM with a two-million-token context window, and ask it to write a feature or explain the architecture. In my experience, this AI guesswork introduces two critical points of failure:

- **The context trap.** LLMs inherently drop attention. If you throw a huge codebase into a model, it will inevitably skip vital context (see: [*"Found in the Middle: Calibrating Positional Attention Bias Improves Long Context Utilization"*](https://arxiv.org/abs/2406.16008)).
- **Run-to-run inconsistency.** If you run the exact same prompt over a massive codebase twice, you get partial, fragmented truths. On iteration one it catches one dependency; on iteration two it catches another.

You cannot build a defensible, governed enterprise system on top of a stochastic foundation where the output changes every time you press enter.

This is why I built the **Brownfield Context Builder**. Instead of trusting LLM prose to understand our architecture, the Builder relies on a deterministic CLI and agent harness. It reads codebases via git history and actual import graphs, pinning AI claims directly to the code and separating verifiable facts from hallucinated inferences. The deterministic approach returns the same well-grounded answer over the same codebase every time. It creates a strict architectural boundary that prevents the catastrophic failures associated with blind LLM trust.

## 2. The Consult Discovery Protocol (CDP): validating reality early

The first failure point of any enterprise AI initiative happens long before a line of code is written. It happens in the scoping phase. Teams routinely substitute hours of speculative conversation for actual technical validation, resulting in months of misguided development.

To counter this, I implemented the **Consult Discovery Protocol (CDP)**: an installable Copilot agent framework that standardizes how we approach new initiatives. It acts as a forcing function that captures structured stakeholder input into standardized artifacts.

Crucially, CDP features a hard "STOP-gate" for brownfield and legacy environments. When stakeholders want to build fast, they often view governance or deep discovery as a roadblock. I reframe it: CDP is about aggressively making assumptions explicit.

Rather than relying on theoretical requirements, we use the shaping conversations to gather data, refine our understanding, and immediately build early prototypes. Those prototypes then become the input for the *next* conversation. By running these quick checks with friendly users before we engage heavy engineering resources, we validate our path. We stop talking about what the AI *might* do and start looking at what it *actually* does within our constraints.

## 3. Cultural engineering via inner source

You can have the best discovery protocols and deterministic pipelines in the world, but if the engineering culture refuses to adopt them, you have failed.

The root cause of resistance in AI adoption is that people still view AI as a simple chat interface — a blank box where they drop in a thought and get a moderately hallucinated output. If every engineer starts from a blank prompt every morning, you have zero consistency, zero governance, and massive duplicated effort.

As the champion for this area, I led the build of an organization-wide AI engineering enablement platform based on the [inner-source](https://about.gitlab.com/topics/version-control/what-is-innersource/) model. Rather than enforcing top-down mandates, I designed it around a "pull, not push" philosophy.

The platform acts as a centralized repository where engineers — and anyone willing to build on their work — can pull pre-validated snippets, specialized skills, optimized prompts, and verified plugins. We proved to our engineers that reusing these existing solutions saves immense time and frustration compared to rebuilding from scratch every day.

By treating our AI interactions as engineered, version-controlled assets rather than disposable chat logs, we ensure that once a specific operational area is covered, it stays covered consistently. The organization adopts the governance not because it is forced to, but because the "golden paths" provided by the common repository are the fastest, most reliable way to get the work done.

---

## The path forward: from pilots to production

Moving an organization into the AI-first era requires more than API access to the latest foundation model. It requires acknowledging that AI delivery is, at its core, rigorous software engineering.

### Vibe coding vs. an architected operating model

- **Discovery**
  - *Vibe coding:* assumptions and endless meetings.
  - *Architected model (CDP):* rapid prototyping, explicit constraints, and friendly-user validation.
- **Architecture**
  - *Vibe coding:* massive context windows and LLM guesswork.
  - *Architected model (Brownfield Builder):* deterministic git-history and import-graph analysis.
- **Culture**
  - *Vibe coding:* AI as an ad-hoc, isolated chat interface.
  - *Architected model (inner source):* AI as an inner-sourced repository of repeatable, engineered assets.

We have to stop chatting and start architecting. By enforcing structured discovery, demanding deterministic technical boundaries in legacy environments, and building a culture of inner-sourced reuse, we can finally stop abandoning fragile pilots and start operating in defensible, governed production.
