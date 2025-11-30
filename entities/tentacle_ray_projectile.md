---
title: Tentacle Ray Projectile
category: entities
---

# Tentacle Ray Projectile

This entity defines a projectile that behaves like a tentacle ray. It is primarily controlled by a Lua script.

## Lua Component

The `LuaComponent` is the core of this entity's behavior.

### Key Attributes

*   `script_source_file`: Specifies the Lua script responsible for the projectile's logic.
    *   Value: `data/scripts/projectiles/tentacle_ray.lua`
*   `execute_every_n_frame`: Determines how often the script's logic is executed.
    *   Value: `10` (The script will run every 10 frames).
*   `_enabled`: Controls whether the Lua component is active.
    *   Value: `1` (Enabled).