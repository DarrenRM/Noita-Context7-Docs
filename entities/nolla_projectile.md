---
title: Nolla Projectile
category: entities
---

---

# Nolla Projectile

This entity defines a special projectile in Noita, primarily used for its unique "Nolla" effect.

## LuaComponent

This component links the entity to its behavior defined in a Lua script.

### Key Attributes:

*   **script\_source\_file**: `data/scripts/projectiles/nolla.lua` - Specifies the Lua script that controls the projectile's logic.
*   **execute\_every\_n\_frame**: `1` - The script will execute every single frame.
*   **remove\_after\_executed**: `1` - The projectile entity will be removed from the game world after its script has executed once.

## Entity

The root element for this entity. It contains the `LuaComponent` to define its behavior.