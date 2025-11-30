---
title: Larpa Chaos Projectile
category: entities
---

# Larpa Chaos Projectile

This entity defines a projectile with chaotic behavior, managed by a Lua script.

## Key Components

### LuaComponent
This component enables the entity to execute custom Lua scripting.

*   **script\_source\_file**: `data/scripts/projectiles/larpa_chaos.lua` - Specifies the Lua script that controls the projectile's behavior.
*   **execute\_every\_n\_frame**: `10` - The script will be executed every 10 frames.

### LifetimeComponent
This component governs how long the entity persists.

*   **lifetime**: `300` - The projectile will exist for 300 frames.