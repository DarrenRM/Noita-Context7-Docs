---
title: Clipping Shot Projectile
category: entities
---

# Clipping Shot Projectile

This entity defines a projectile with clipping capabilities, meaning it can pass through certain objects.

## Key Components

### LuaComponent
This component is responsible for the projectile's behavior.

*   **script_source_file**: `data/scripts/projectiles/clipping_shot.lua` - Specifies the Lua script that governs the projectile's logic.
*   **execute_every_n_frame**: `1` - The script will execute every frame.
*   **remove_after_executed**: `1` - The projectile entity will be removed after the script has executed once.