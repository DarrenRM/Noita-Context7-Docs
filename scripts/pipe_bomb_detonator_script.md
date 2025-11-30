---
title: Pipe Bomb Detonator Script
category: scripts
---

# Pipe Bomb Detonator Script

This script is responsible for the detonation logic of pipe bombs in Noita. When a pipe bomb entity is spawned, this script is attached to it.

## Core Functionality

The primary function of this script is to:

1.  **Destroy existing pipe bombs:** It first checks for any existing entities tagged as "pipe_bomb" and destroys them. This is likely a cleanup mechanism to prevent multiple pipe bombs from existing simultaneously or to ensure a fresh spawn.
2.  **Destroy itself:** After the cleanup, it destroys the entity it is attached to, effectively causing the pipe bomb to detonate.

## Key Elements

*   **`EntityGetWithTag("pipe_bomb")`**: This function retrieves all entities currently present in the game world that have the tag "pipe_bomb".
*   **`for i,v in ipairs(pipe_bombs) do ... EntityKill(v) end`**: This loop iterates through the found pipe bomb entities and destroys each one using `EntityKill()`.
*   **`GetUpdatedEntityID()`**: This function retrieves the unique identifier of the entity that this script is currently attached to.
*   **`EntityKill(entity_id)`**: This function destroys the entity identified by `entity_id`, which in this context is the pipe bomb itself, triggering its detonation.

## Usage

This script is intended to be attached to a pipe bomb entity. Its execution leads to the destruction of other pipe bombs and the detonation of the pipe bomb it is attached to.