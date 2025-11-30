---
title: Fire Essence Projectile Behavior
category: scripts
---

# Fire Essence Projectile Behavior

This script defines the behavior of a projectile that spawns when a "Fire Essence" is used.

## Core Functionality

When this script is attached to an entity (presumably a projectile representing a Fire Essence), it performs the following actions:

### Projectile Spawning

*   **`shoot_projectile( parent_id, "data/entities/misc/essences/fire_explosion.xml", pos_x, pos_y, 0, 0 )`**: This is the primary function. It spawns a new projectile entity.
    *   **`parent_id`**: The ID of the entity that spawned this projectile (e.g., the wand or player).
    *   **`"data/entities/misc/essences/fire_explosion.xml"`**: The XML file defining the appearance and behavior of the spawned projectile. This indicates that a "fire explosion" entity will be created.
    *   **`pos_x, pos_y`**: The X and Y coordinates where the new projectile will be spawned, matching the current position of the Fire Essence projectile.
    *   **`0, 0`**: These likely represent the initial velocity components (X and Y) for the spawned projectile. In this case, it's spawned with no initial velocity relative to its spawn point.

### Contextual Check

*   **`if (parent_id ~= NULL_ENTITY) then ... end`**: This conditional statement ensures that the `shoot_projectile` function is only called if the current entity has a valid parent. This prevents errors if the script is somehow executed without a proper parent entity.

## Key Elements

*   **Essence Type**: Fire
*   **Action**: Spawns a secondary projectile/effect.
*   **Secondary Effect**: `fire_explosion.xml` (indicates a fiery explosion visual and/or damage effect).
*   **Spawn Location**: Matches the location of the Fire Essence projectile.
*   **Parent Dependency**: Requires a valid parent entity to function.