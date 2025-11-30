---
title: Chest Rain Entity
category: entities
---

# Chest Rain Entity

This entity defines a mechanism for spawning chests periodically. It's primarily controlled by a Lua script that handles the actual spawning logic.

## Key Components

### LifetimeComponent

*   **lifetime**: The duration in frames this entity will exist.
    *   `300` frames (approximately 5 seconds).
*   **serialize_duration**: How long the entity's duration should be serialized.
    *   `1` frame.

### LuaComponent

*   **_enabled**: Whether the Lua component is active.
    *   `1` (enabled).
*   **execute_every_n_frame**: The interval in frames between script executions.
    *   `20` frames.
*   **script_source_file**: The path to the Lua script responsible for the entity's behavior.
    *   `data/scripts/buildings/spawn_chests.lua`

## Inherited Components

*   **InheritTransformComponent**: Indicates that this entity inherits transform properties from its parent or environment.

## Usage Notes

This entity is designed to be a trigger or a manager for spawning chests. The core logic for *what* chests are spawned and *where* they appear is handled within the `spawn_chests.lua` script. Modders looking to customize chest spawning should focus on modifying this Lua script.