---
title: Avoiding Arc Projectile
category: entities
---

# Avoiding Arc Projectile

This entity defines a projectile with a Lua-based behavior for avoiding obstacles.

## LuaComponent

This component is responsible for the projectile's dynamic behavior.

### Key Attributes:

*   **script_source_file**: `data/scripts/projectiles/avoiding_arc.lua` - Specifies the Lua script that controls the projectile's logic.
*   **execute_every_n_frame**: `3` - The script will be executed every 3 frames, allowing for frequent updates to the projectile's movement and avoidance.

## Purpose

The `avoiding_arc.lua` script (referenced by this entity) likely implements logic for the projectile to detect and steer around environmental obstacles, creating an "avoiding arc" effect. This is useful for projectiles that need to navigate complex environments without immediately colliding.