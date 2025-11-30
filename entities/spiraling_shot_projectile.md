---
title: Spiraling Shot Projectile
category: entities
---

# Spiraling Shot Projectile

This entity defines a projectile with a spiraling movement pattern, controlled by an associated Lua script.

## Key Components

### LuaComponent
This component is responsible for the projectile's behavior.

*   **`script_source_file`**: `data/scripts/projectiles/spiraling_shot.lua`
    *   This specifies the Lua script that governs the projectile's movement and effects.
*   **`execute_every_n_frame`**: `1`
    *   The script logic will be executed every frame, allowing for continuous updates to the projectile's trajectory.