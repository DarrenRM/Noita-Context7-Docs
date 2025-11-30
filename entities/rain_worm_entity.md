---
title: Rain Worm Entity
category: entities
---

# Rain Worm Entity

This document describes the `rain_worm.xml` entity, which defines the behavior and properties of the Rain Worm in Noita.

## Key Components

The Rain Worm entity is primarily defined by the following components:

### InheritTransformComponent

This component indicates that the entity inherits its transform properties (position, rotation, scale) from its parent.

### LifetimeComponent

*   **lifetime**: `120`
    *   Specifies the duration in seconds for which the Rain Worm entity will exist.

### LuaComponent

*   **_enabled**: `1`
    *   Enables the Lua script associated with this component.
*   **execute_every_n_frame**: `20`
    *   The associated Lua script will execute its logic every 20 frames.
*   **script_source_file**: `data/scripts/streaming_integration/scripts/rain_worm.lua`
    *   This attribute points to the external Lua script that governs the Rain Worm's behavior, AI, and interactions.

## Associated Lua Script

The behavior of the Rain Worm is controlled by the script located at `data/scripts/streaming_integration/scripts/rain_worm.lua`. This script would typically handle:

*   Movement patterns (e.g., falling from the sky).
*   AI logic (e.g., targeting players, attacking).
*   Visual effects and animations.
*   Sound effects.
*   Damage and interaction with the game world.