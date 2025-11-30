---
title: Worm Rain Entity
category: entities
---

# Worm Rain Entity

This entity defines a mechanism for spawning worms periodically, simulating a "worm rain" effect.

## Key Components

### LifetimeComponent
Controls how long the entity persists.

*   **lifetime**: `300` (seconds) - The total duration the entity will exist.
*   **serialize_duration**: `1` - How often the duration is saved.

### LuaComponent
Executes a Lua script to handle the worm spawning logic.

*   **_enabled**: `1` - Ensures the component is active.
*   **execute_every_n_frame**: `20` - The script will run every 20 frames.
*   **script_source_file**: `data/scripts/animals/spawn_worms.lua` - The path to the Lua script responsible for spawning worms.

## Inheritance

*   **InheritTransformComponent**: Indicates that this entity inherits transform properties, likely for positioning and movement within the game world.