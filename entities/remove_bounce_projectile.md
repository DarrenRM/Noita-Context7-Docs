---
title: Remove Bounce Projectile
category: entities
---

---

# Remove Bounce Projectile

This entity defines a projectile that, upon collision, will remove its bounce behavior. This is typically used for projectiles that should only hit once or have a specific impact effect without ricocheting.

## Key Components

### LuaComponent

This component is responsible for the projectile's behavior.

*   **`script_source_file`**: `data/scripts/projectiles/remove_bounce.lua`
    *   Specifies the Lua script that handles the projectile's logic.
*   **`execute_every_n_frame`**: `1`
    *   The script will execute every frame.
*   **`remove_after_executed`**: `1`
    *   The entity (and its associated projectile) will be removed from the game world immediately after the script has executed.

## Usage

This entity is intended to be instantiated as a projectile. When this projectile collides with an object, the associated Lua script will trigger, causing the projectile to cease bouncing. This is a fundamental building block for creating projectiles with unique impact mechanics.