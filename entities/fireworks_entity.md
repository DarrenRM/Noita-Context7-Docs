---
title: Fireworks Entity
category: entities
---

# Fireworks Entity

This entity defines a basic fireworks effect. It primarily relies on a Lua script to manage its behavior and visual output.

## Key Components

### LifetimeComponent
Controls how long the entity exists.

*   **lifetime**: The duration in frames the entity will persist.

### LuaComponent
Attaches a Lua script to the entity, enabling custom logic.

*   **_enabled**: Whether the Lua component is active.
*   **execute_every_n_frame**: How often the attached script's `on_frame` function is called.
*   **script_source_file**: The path to the Lua script that governs the fireworks' behavior.

## Lua Script (`fireworks.lua`)

The `fireworks.lua` script is responsible for the actual visual generation and behavior of the fireworks. While the XML defines the entity's existence and script attachment, the Lua script handles:

*   Spawning particles.
*   Defining particle behavior (movement, color, lifespan).
*   Creating explosion effects.
*   Timing and sequencing of the fireworks display.

**Note:** The specific implementation details of `fireworks.lua` are not provided in this XML, but it's the core of the fireworks functionality.