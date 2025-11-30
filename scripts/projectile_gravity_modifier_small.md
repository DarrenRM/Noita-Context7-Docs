---
title: Projectile Gravity Modifier (Small)
category: scripts
---

# Projectile Gravity Modifier (Small)

This script modifies the velocity of nearby projectiles, applying a gravity-like pull towards the entity executing this script. The effect is stronger for projectiles closer to the entity.

## Key Functionality

This script iterates through all entities tagged as "projectile" and applies a directional force to them if they are within a certain range.

### Core Attributes & Logic

*   **`entity_id`**: The unique identifier of the entity executing this script.
*   **`x`, `y`**: The world coordinates of the executing entity.
*   **`projectiles`**: A table containing the IDs of all entities tagged as "projectile".
*   **`distance_full`**: A base distance threshold (72 units) used for calculating gravity strength.
*   **`gravity_coeff`**: A multiplier (112) that scales the gravity effect.
*   **`gravity_percent`**: Calculated based on the distance to the projectile. It ranges from 0.2 (for projectiles at `distance_full`) up to 1.0 (for projectiles very close).
*   **`direction`**: The angle from the projectile towards the executing entity.
*   **`velocitycomponents`**: Retrieves the `VelocityComponent` of a projectile, which controls its movement.
*   **`edit_component`**: A utility function to modify the `VelocityComponent` of a projectile.
*   **`ComponentGetValueVector2` / `ComponentSetValueVector2`**: Functions used to read and write the `mVelocity` (x and y components) of the `VelocityComponent`.

### Logic Flow

1.  Get the ID and transform of the entity running the script.
2.  Find all entities tagged as "projectile".
3.  For each projectile:
    *   Calculate the Manhattan distance and then the Euclidean distance to the executing entity.
    *   If the projectile is within a slightly extended range (`distance_full * 1.25`) and is not the executing entity itself:
        *   Calculate the direction towards the executing entity.
        *   If the projectile is within the primary range (`distance_full`):
            *   Get the projectile's `VelocityComponent`.
            *   Calculate the `gravity_percent` based on how close the projectile is.
            *   Calculate the directional offset (`offset_x`, `offset_y`) based on the direction, `gravity_coeff`, and `gravity_percent`.
            *   Add this offset to the projectile's current velocity.
            *   Update the projectile's velocity.

### Example Usage (Conceptual)

This script would typically be attached to a projectile or an entity that should exert a gravitational pull on other projectiles. For instance, a "gravity well" projectile could use this script to pull other projectiles towards it.

```lua
-- Example of how this script might be applied to an entity
-- (This is illustrative and not part of the provided script)

-- In an entity's .xml definition:
-- <entity name="gravity_well_projectile">
--     <components>
--         <component name="projectile" />
--         <component name="script_emitter_ray" script_name="data/scripts/projectiles/projectile_gravity_small.lua" />
--         <!-- Other components -->
--     </components>
-- </entity>
```