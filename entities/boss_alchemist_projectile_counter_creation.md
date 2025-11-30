---
title: Boss Alchemist Projectile Counter Creation
category: entities
---

---

# Boss Alchemist Projectile Counter Creation

This script is responsible for creating and initializing the projectile counter entity used by the Boss Alchemist.

## Core Functionality

The script performs the following key actions:

1.  **Entity Initialization**: Retrieves the current entity's ID and its world coordinates.
2.  **Projectile Counter Loading**: Loads the `projectile_counter.xml` entity at the Boss Alchemist's position.
3.  **Child Entity Association**: Makes the loaded projectile counter a child of the Boss Alchemist entity.
4.  **Lua Component Configuration**:
    *   Finds the `LuaComponent` named "counter" on the Boss Alchemist.
    *   Sets `execute_every_n_frame` to `600` for this component, controlling its update frequency.
5.  **Hitbox Component Modification**:
    *   Locates the `HitboxComponent` on the Boss Alchemist.
    *   Sets `damage_multiplier` to `0.0`, ensuring this hitbox does not deal damage.

## Key Components and Attributes

### `LuaComponent` (counter)

*   **`execute_every_n_frame`**: `600` - Determines how often the Lua script associated with this component will execute.

### `HitboxComponent`

*   **`damage_multiplier`**: `0.0` - This hitbox is non-damaging.

## Related Files

*   `data/entities/animals/boss_alchemist/projectile_counter.xml`: The XML definition for the projectile counter entity itself.
*   `data/scripts/lib/utilities.lua`: A utility script likely used for helper functions.