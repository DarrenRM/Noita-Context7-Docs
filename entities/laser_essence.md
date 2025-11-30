---
title: Laser Essence
category: entities
---

# Laser Essence

This entity defines the "Laser" essence in Noita, a special effect that can be applied to wands.

## Core Components

*   **`InheritTransformComponent`**: This component indicates that the essence will inherit transform properties from its parent entity (likely a wand).

*   **`LuaComponent`**: This is the primary component responsible for the essence's behavior.
    *   **`_enabled`**: Set to `1`, meaning the Lua script is active.
    *   **`execute_every_n_frame`**: Set to `120`. This means the associated Lua script (`data/scripts/essences/laser.lua`) will execute its logic once every 120 frames. This controls the frequency of the laser effect.
    *   **`script_source_file`**: Specifies the path to the Lua script that governs the essence's functionality: `data/scripts/essences/laser.lua`.

## Functionality (Inferred from `script_source_file`)

The `laser.lua` script is responsible for the actual implementation of the laser effect. Based on the `execute_every_n_frame` setting, it's likely that this script:

*   Generates a laser beam or projectile.
*   Applies damage or other effects to entities hit by the laser.
*   Manages the visual and auditory aspects of the laser.
*   Potentially has a cooldown or duration mechanism tied to the `execute_every_n_frame` value.