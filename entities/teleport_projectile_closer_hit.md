---
title: Teleport Projectile Closer Hit
category: entities
---

# Teleport Projectile Closer Hit

This entity defines the behavior for a projectile that, upon hitting a target, teleports the target closer to the projectile's origin.

## LuaComponent

This component links the entity to its associated Lua script, which handles the actual teleportation logic.

### Key Attributes:

*   **`script_source_file`**: `data/scripts/projectiles/teleport_projectile_closer_hit.lua`
    *   Specifies the Lua script responsible for the projectile's behavior.
*   **`execute_on_added`**: `1`
    *   Indicates that the script should be executed immediately when the entity is added to the game world.
*   **`remove_after_executed`**: `1`
    *   Ensures that this projectile entity is removed from the game world after its script has finished executing.