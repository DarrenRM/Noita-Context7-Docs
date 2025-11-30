---
title: Teleport Cast Projectile
category: scripts
---

---

# Teleport Cast Projectile

This script defines the behavior of a projectile that teleports the caster to a nearby target.

## Core Functionality

The primary function of this script is to:
1.  Identify nearby entities tagged as "homing_target".
2.  Randomly select one of these targets.
3.  Teleport the caster (the entity executing this script) to the selected target's location.

## Key Attributes & Logic

*   **`entity_id`**: Retrieves the unique identifier of the entity executing this script.
*   **`pos_x`, `pos_y`**: Gets the current position of the caster.
*   **`targets = EntityGetInRadiusWithTag( pos_x, pos_y, 96, "homing_target" )`**: This is the core targeting mechanism. It searches for entities within a 96-pixel radius of the caster that possess the "homing_target" tag.
*   **`if ( #targets > 0 ) then ... end`**: This conditional block ensures that teleportation only occurs if at least one valid target is found.
*   **`local rnd = Random(1, #targets)`**: A random number is generated to select an index from the `targets` array.
*   **`local target_id = targets[rnd]`**: The ID of the randomly selected target is retrieved.
*   **`local tx, ty = EntityGetFirstHitboxCenter( target_id )`**: The center coordinates of the selected target's hitbox are obtained.
*   **`EntitySetTransform( entity_id, tx, ty )`**: The caster's transform (position) is updated to match the target's center coordinates, effectively teleporting the caster.

## Dependencies

*   `data/scripts/lib/utilities.lua`: This file is included for potential utility functions, though none are explicitly called in this snippet.

## Usage Notes

This script is intended to be attached to a projectile entity that should have a teleporting effect. The projectile itself would need to be configured to execute this script upon its creation or impact. The "homing_target" tag is crucial for identifying entities that can be teleported to.