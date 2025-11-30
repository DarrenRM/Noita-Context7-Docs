---
title: Larpa Upwards Projectile
category: entities
---

# Larpa Upwards Projectile

This entity defines a projectile that travels upwards, likely used for specific spell effects or enemy attacks.

## Key Components

### LuaComponent
This component links the entity to a Lua script that controls its behavior.

*   **script\_source\_file**: `data/scripts/projectiles/larpa_upwards.lua` - Specifies the Lua script responsible for the projectile's logic.
*   **execute\_every\_n\_frame**: `10` - The script will execute its logic every 10 frames.

### LifetimeComponent
This component determines how long the projectile will exist before despawning.

*   **lifetime**: `300` - The projectile will exist for 300 frames.