*Read this in [English](README.md) | Читать на [Русском](README.ru.md)*

# Telegram AI Companion: Narrative Engine

**Status:** Live (Private B2C Project)  
**Platform:** Telegram PWA (Mini App)

## Overview
This repository contains the **raw, production-used system prompts** and state machine logic for an 18+ character-driven AI companion inside a Telegram Mini App. 

The core engineering challenge was preventing the LLM from generating cliché, overly romanticized "AI slop" by enforcing strict psychological progression, physical physics, and hard content caps.

## ⚙️ Core Architecture (Working Files)

All prompts are in Russian (the native language of the product) and demonstrate the actual logic injected into the LLM during runtime.

### 1. Finite State Machine (FSM) Pacing
The AI's arousal and behavior are controlled by a mathematical progression scale (`yielding_progress`). The orchestrator evaluates user inputs and dynamically swaps prompt states.
*   📄 **[Pacing Logic: Diana (Scene 1)](prompts/pacing_diana_scene_1.md)** — Shows the increment matrix (+0 to +25) and dynamic mood mapping.
*   📄 **[Pacing Logic: Kira (Scene 2)](prompts/pacing_kira_scene2.md)** — Shows hard caps (blocking content) and forced interrupt events triggered by specific point thresholds.

### 2. Persona Configuration & "Anti-Slop" Directing
Instead of basic character sheets, personas are mapped with specific triggers (Body Betrayal, Ruin & Mess) and strict negative constraints to prevent LLM hallucinations.
*   📄 **[Core Persona: Diana](prompts/diana-character.md)** — Deep psychological mapping, non-verbal signals, and psychosexual profile.
*   📄 **[NSFW Module: Diana](prompts/diana-character-nsfw.md)** — Mapping the LLM output into strict JSON formats (`action_and_body`, `internal_monologue`, `direct_speech`).
*   📄 **[Scene Directors](prompts/scene_director_diana_1.md)** — Short prompt injections forcing the LLM to focus on dry physical reality instead of flowery metaphors.

### 3. UI Synchronization
Mapping the LLM narrative progression to the Telegram frontend (Push notifications, Video-Circles, and Chat UI).
*   📄 **[Telegram UI Flow](prompts/Diana-UI-Scene1.txt)**
