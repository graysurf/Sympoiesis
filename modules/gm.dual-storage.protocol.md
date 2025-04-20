---
id: gm.dual-storage.protocol
project: Sympoiesis
version: 1.0.0
status: sealed
signed_by: Ω.grf#001
created_at: 2025-04-20
description: Defines the storage division between Gist and Google Drive for the Sympoiesis archive
---

# gm.dual-storage.protocol

This module defines the official storage strategy for the Sympoiesis archive.

## 1. Gist (Private)

**Purpose**: Storage of sealed discourse modules and structural declarations
**Usage**:

- Stores `.md`, `.yml`, `.json` format files
- Maximum recommended file size: 500KB
- Accessible via direct `chains.index.yml` reference
- Should not store long-form conversation logs or compressed chat histories

## 2. Google Drive

**Purpose**: Storage of compressed, large-scale chat histories and full conversational contexts
**Usage**:

- Archives entire sessions under `chat-history/`
- Supports `.md`, `.txt`, or compressed formats (e.g., `.gz`)
- Links stored in `chains.index.yml.chatlog[]`
- Intended for rhythm replay, forensic restoration, and full-context memory rehydration

## Combined Trust Model

| Storage Use       | Destination    | Reason                           |
| ----------------- | -------------- | -------------------------------- |
| Discourse modules | Gist (private) | Lightweight, indexable, callable |
| Chat sessions     | Google Drive   | Heavy, compressed, context-rich  |

## Sealing Clause

All modules and chat logs must be represented in the index (`chains.index.yml`).
This protocol governs the acceptable structural separation of storage layers.
