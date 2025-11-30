---
title: Bounce Larpa Launcher Projectile
category: entities
---

# Bounce Larpa Launcher Projectile

This entity defines the behavior of a projectile fired by the "Bounce Larpa Launcher". It's designed to be a persistent projectile that can penetrate both entities and the world.

## Key Components

### LuaComponent

This component links the projectile to its associated Lua script, which handles its specific logic.

*   **script_source_file**: `data/scripts/projectiles/bounce_larpa_launch.lua` - The path to the Lua script that governs the projectile's behavior.
*   **execute_on_added**: `1` - Indicates that the Lua script should execute immediately when the projectile is added to the game world.

### ProjectileComponent

This component defines the fundamental properties of the projectile.

*   **_tags**: `enabled_in_world` - Ensures this projectile is active and functional within the game world.
*   **lifetime**: `-1` - The projectile has an indefinite lifetime, meaning it won't disappear on its own unless explicitly removed by game logic.
*   **penetrate_entities**: `1` - The projectile can pass through other entities without stopping.
*   **penetrate_world**: `1` - The projectile can pass through the game's environment (walls, terrain, etc.) without stopping.
*   **damage**: `0.0` - This projectile deals no direct damage. Its purpose is likely related to its bouncing or other effects defined in its Lua script.
*   **do_moveto_update**: `0` - Disables the default "move to" update behavior for projectiles, suggesting custom movement logic is handled by the Lua script.

### VelocityComponent

This component is present to enable velocity-related properties, though specific values are not defined here, implying they are likely set by the associated Lua script.