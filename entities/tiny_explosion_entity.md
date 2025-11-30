---
title: Tiny Explosion Entity
category: entities
---

# Tiny Explosion Entity

This entity defines a small, ephemeral explosion effect. It's primarily driven by a Lua script that handles its behavior and removal.

## Key Components

### LuaComponent

This is the core component responsible for the entity's dynamic behavior.

*   **`script_source_file`**: `data/scripts/projectiles/explosion_tiny.lua`
    *   Specifies the Lua script that controls the explosion's logic.
*   **`execute_every_n_frame`**: `1`
    *   Indicates that the script should execute every frame.
*   **`remove_after_executed`**: `1`
    *   Ensures the entity is removed from the game world after the script has executed its logic (likely once).

## Usage

This entity is typically used to create small visual and potentially minor damage-dealing explosions in the game. The specific effects and behaviors are determined by the `explosion_tiny.lua` script.