---
title: Icer Death Projectile Spawner
category: scripts
---

# Icer Death Projectile Spawner

This script defines the behavior for an entity's death, specifically causing it to spawn multiple ice projectiles.

## Function: `death`

This function is called when the entity associated with this script dies.

### Parameters:

*   `damage_type_bit_field`: (Bitfield) Indicates the type of damage that caused the death.
*   `damage_message`: (String) A message describing the damage.
*   `entity_thats_responsible`: (Entity ID) The entity that inflicted the damage.
*   `drop_items`: (Boolean) Whether to drop items upon death.

### Behavior:

1.  **Get Entity Information**: Retrieves the ID and transform (position) of the dying entity.
2.  **Projectile Spawning**:
    *   Defines `how_many` projectiles to spawn (set to 12).
    *   Calculates the angular increment (`angle_inc`) to distribute projectiles evenly in a circle.
    *   Sets a `length` for the projectile velocity (set to 100).
    *   Iterates `how_many` times:
        *   Calculates the `vel_x` and `vel_y` for each projectile using trigonometry to create a circular spread.
        *   Calls `shoot_projectile` to spawn an "ice.xml" projectile at the entity's position with the calculated velocity.

## Key Elements:

*   **Projectile Type**: `data/entities/projectiles/ice.xml`
*   **Number of Projectiles**: 12
*   **Spread Pattern**: Circular, evenly distributed.
*   **Velocity Magnitude**: 100 units.