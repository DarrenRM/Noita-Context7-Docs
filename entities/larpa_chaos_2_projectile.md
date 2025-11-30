---
title: Larpa Chaos 2 Projectile
category: entities
---

# Larpa Chaos 2 Projectile

This entity defines a projectile with chaotic behavior, controlled by a Lua script.

## Key Components

### LuaComponent
This component links the entity to a Lua script that dictates its behavior.

*   **`script_source_file`**: `data/scripts/projectiles/larpa_chaos_2.lua` - Specifies the script file responsible for the projectile's logic.
*   **`execute_every_n_frame`**: `5` - The script will execute its logic every 5 frames.

### LifetimeComponent
This component determines how long the projectile exists.

*   **`lifetime`**: `200` - The projectile will exist for 200 frames before disappearing.