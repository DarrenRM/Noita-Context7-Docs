---
title: Floating Arc Projectile
category: entities
---

# Floating Arc Projectile

This entity defines a projectile that behaves as a "floating arc." It is primarily controlled by a Lua script.

## Lua Component

The core functionality of this entity is managed by a Lua script.

### `LuaComponent`

*   **`script_source_file`**: `data/scripts/projectiles/floating_arc.lua`
    *   This attribute specifies the path to the Lua script responsible for the projectile's behavior.
*   **`execute_every_n_frame`**: `1`
    *   Indicates that the script's logic should be executed every single frame, allowing for real-time updates and dynamic behavior.