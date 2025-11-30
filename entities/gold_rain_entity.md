---
title: Gold Rain Entity
category: entities
---

# Gold Rain Entity

This entity defines the behavior for gold rain in Noita, primarily managed by a Lua script.

## Core Components

*   **`InheritTransformComponent`**: Inherits transformation properties, likely for positioning and movement within the game world.
*   **`LifetimeComponent`**:
    *   `lifetime`: Specifies the duration this entity exists in frames (200 frames in this case).
*   **`LuaComponent`**:
    *   `_enabled`: Controls whether the Lua script is active (set to 1, meaning enabled).
    *   `execute_every_n_frame`: Determines how often the associated Lua script's `on_frame` function is called (every 5 frames).
    *   `script_source_file`: Points to the Lua script that governs the entity's behavior (`data/scripts/streaming_integration/scripts/rain_gold.lua`).

## Lua Script (`rain_gold.lua`)

The `rain_gold.lua` script is responsible for the actual logic of the gold rain, including:

*   Spawning gold particles.
*   Potentially influencing their trajectory and behavior.
*   Managing the visual and physical effects of gold falling.

**Note:** The specific implementation details of the gold rain's behavior are contained within the `rain_gold.lua` file, which is not provided in this XML snippet.