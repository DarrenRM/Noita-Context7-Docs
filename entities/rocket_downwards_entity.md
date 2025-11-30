---
title: Rocket Downwards Entity
category: entities
---

# Rocket Downwards Entity

This entity defines a projectile that moves downwards. It primarily relies on a Lua script for its behavior.

## Key Components

### LuaComponent
This component links the entity to its behavior script and dictates how frequently it executes.

*   **script\_source\_file**: `data/scripts/projectiles/rocket_downwards.lua` - Specifies the Lua script that controls the entity's logic.
*   **execute\_every\_n\_frame**: `3` - The script will be executed every 3 frames.