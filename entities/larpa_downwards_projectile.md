---
title: Larpa Downwards Projectile
category: entities
---

# Larpa Downwards Projectile

This entity defines a projectile that moves downwards, likely used for specific spell effects or environmental interactions.

## Key Components

### LuaComponent
This component links the entity to a Lua script that controls its behavior.

*   **`script_source_file`**: `data/scripts/projectiles/larpa_downwards.lua` - Specifies the Lua script responsible for the projectile's logic.
*   **`execute_every_n_frame`**: `10` - The script will execute its logic every 10 frames.

### LifetimeComponent
This component determines how long the projectile exists before being removed.

*   **`lifetime`**: `300` - The projectile will exist for 300 frames.