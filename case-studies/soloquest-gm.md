---
layout: single
title: "SoloQuest GM (AntigravityDM) — AI-driven local RPG platform"
permalink: /case-studies/soloquest-gm/
---

## Overview

SoloQuest GM (AntigravityDM) is a local desktop application and MVP that functions as an AI-powered Dungeon Master. The system emphasizes structured game memory, typed game state, and controlled agent workflows rather than freeform model narration.

## My role

Lead architect / product lead (MVP)

## What makes it interesting

- Desktop app built with Tauri + Rust + React + TypeScript.
- Adventure content is authored in Markdown; the app parses, indexes and uses it as structured game context.
- File-based memory stores rules, lore, NPCs, quests, and session history locally in Markdown/JSON.
- Retrieval layer searches and reads precise content fragments relevant to the current turn.
- Typed game state (character stats, inventory, spell slots, world state) is updated through structured tools rather than freeform model output.
- Agent flow: model runs with a defined toolset and accesses only the context required for the moment.

## Architecture & stack

- UI: React + TypeScript (desktop via Tauri)
- Core: Rust for local runtime, persistence, and performance-sensitive components
- Memory/storage: local Markdown/JSON modules with structured parsers and indexes
- Retrieval: local search/indexing layer that provides precise fragments for the LLM
- LLM/agents: model orchestration with tool calls and controlled context windows

## MVP features

- Load Markdown campaign modules and run persistent sessions with consistent state.
- Fine-grained retrieval and memory (memory != chat history).
- Typed state updates and deterministic tool-driven game mechanics.

## Roadmap (next stages)

- PDF import and automated content processing for larger adventure sources
- Cloud sync and account layer for shared campaigns
- Premium subscriptions and shared campaign features
- Scalable retrieval infrastructure for cloud-hosted workflows

## Outcomes & lessons

- Demonstrates a clear AI product architecture that separates memory, retrieval, and agent behavior from chat-like interaction.
- Shows how file-first local memory plus typed state and retrieval enables consistent, composable gameplay.

---

If you'd like, I can expand this with diagrams, sample data formats (example Markdown module and JSON state), or a demo flow for a turn.