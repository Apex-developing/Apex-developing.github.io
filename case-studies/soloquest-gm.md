---
layout: single
title: "SoloQuest GM (AntigravityDM) — Applied AI Product"
permalink: /case-studies/soloquest-gm/
---

## Overview

SoloQuest GM (AntigravityDM) is a local-first desktop MVP exploring how LLMs can be turned into a reliable product component rather than used only for freeform conversation. The application acts as an AI-powered Dungeon Master while separating persistent knowledge, retrieval, game state, and agent behavior into distinct parts of the system.

The project is both a product prototype and a practical exploration of AI application architecture: how to control context, maintain state, use tools, and build predictable workflows around an LLM.

## My role

Lead architect / product lead (MVP)

## What makes it interesting

- Designed as a local-first desktop application using Tauri + Rust + React + TypeScript.
- Adventure content is authored in Markdown and parsed, indexed, and supplied as structured context rather than sent wholesale to the model.
- File-first memory stores rules, lore, NPCs, quests, and session history locally in Markdown/JSON.
- A retrieval layer finds precise content fragments relevant to the current turn.
- Typed game state — including character statistics, inventory, spell slots, and world state — is updated through structured tools rather than freeform model output.
- The agent operates through a defined toolset and receives only the context required for the current task.

## Architecture & stack

- **UI:** React + TypeScript, packaged as a desktop application through Tauri
- **Core:** Rust for local runtime, persistence, and performance-sensitive components
- **Memory & storage:** local Markdown/JSON modules with structured parsers and indexes
- **Retrieval:** local search/indexing layer providing focused context to the LLM
- **LLM & agents:** model orchestration through tool calls and controlled context windows

The architecture intentionally separates several concerns that are often collapsed into a single chat history: **knowledge, retrieval, memory, state, tools, and agent behavior**.

## MVP features

- Load Markdown campaign modules and run persistent sessions with consistent state
- Fine-grained retrieval and persistent memory — memory is not treated as chat history
- Typed state updates and deterministic tool-driven game mechanics
- Local-first data and application runtime

## Product & engineering decisions

The central design decision was to avoid making the LLM the authority for everything. The model interprets intent and selects actions, while structured tools and application state remain responsible for deterministic updates.

This creates a clearer boundary between probabilistic model behavior and deterministic application logic, making the system easier to reason about, test, and extend.

## Roadmap (next stages)

- PDF import and automated content processing for larger adventure sources
- Cloud sync and account layer for shared campaigns
- Premium subscriptions and shared campaign features
- Scalable retrieval infrastructure for cloud-hosted workflows

## Outcomes & lessons

- Demonstrates a practical architecture for building AI applications around an LLM rather than around a chat interface.
- Separates persistent memory, retrieval, agent behavior, and deterministic application state.
- Explores how tool calling and structured state can make agent-driven applications more predictable and composable.
- Provides a working foundation for extending a local AI prototype toward a broader product architecture.
