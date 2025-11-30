---
title: Giga Discs Effect Entity
category: entities
---

# Giga Discs Effect Entity

This entity defines the behavior and properties of the "Giga Discs" effect in Noita. It primarily relies on a Lua script for its functionality.

## Key Components

### LuaComponent
This is the core component responsible for the entity's dynamic behavior.

*   **`script_source_file`**: Specifies the Lua script that controls the entity's logic.
    *   `data/scripts/streaming_integration/scripts/effect_giga_discs.lua`
*   **`execute_every_n_frame`**: Determines how frequently the Lua script's `update` function is called.
    *   `3` (The script will execute every 3 frames).

### LifetimeComponent
This component manages how long the entity persists in the game world.

*   **`lifetime`**: The duration in seconds the entity will exist before being removed.
    *   `3600` (This is a very long lifetime, effectively making it persistent until explicitly removed by other game mechanics or scripts).

### InheritTransformComponent
This component indicates that the entity will inherit transformation properties (like position, rotation, scale) from its parent entity. This is common for effects that are attached to or spawned by other entities.