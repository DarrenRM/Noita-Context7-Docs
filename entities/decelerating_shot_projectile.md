---
title: Decelerating Shot Projectile
category: entities
---

# Decelerating Shot Projectile

This entity defines a projectile that decelerates over time.

## LuaComponent

This component attaches a Lua script to the entity, controlling its behavior.

### Key Attributes:

*   **script\_source\_file**: `data/scripts/projectiles/decelerating_shot.lua` - Specifies the Lua script responsible for the projectile's logic.
*   **execute\_every\_n\_frame**: `1` - The script will execute every frame.
*   **remove\_after\_executed**: `1` - The entity will be removed after the script has executed once.