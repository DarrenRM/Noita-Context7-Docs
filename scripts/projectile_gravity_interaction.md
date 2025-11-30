---
title: Projectile Gravity Interaction
category: scripts
---

# Projectile Gravity Interaction

This script modifies the behavior of projectiles by applying a gravity-like pull towards other projectiles within a certain range. It aims to create dynamic interactions between projectiles in the game.

## Core Functionality

The script iterates through all entities tagged as "projectile". For each projectile, it checks its proximity to the entity running this script. If another projectile is within a defined range, a gravitational force is calculated and applied to its velocity.

### Key Attributes and Elements

*   **`entity_id`**: The unique identifier of the entity running this script.
*   **`projectiles`**: A table containing the IDs of all entities tagged as "projectile".
*   **`distance_full`**: A base distance value (96 pixels) used for calculating gravity strength.
*   **`gravity_coeff`**: A multiplier (96) that scales the gravitational force.
*   **`VelocityComponent`**: The component that stores and allows modification of an entity's velocity.

### Logic Breakdown

1.  **Get Current Projectile**: The script first identifies the entity it's attached to and its position.
2.  **Find Other Projectiles**: It then searches for all other entities tagged as "projectile".
3.  **Proximity Check**: For each other projectile, it calculates the distance.
4.  **Range and Exclusion**: It only considers projectiles within a slightly extended range (`distance_full * 1.25`) and excludes the projectile itself.
5.  **Gravity Calculation**:
    *   If a projectile is within the `distance_full` range, the script calculates the direction and magnitude of the gravitational pull.
    *   The strength of the pull is inversely proportional to the distance, meaning closer projectiles exert a stronger force.
6.  **Velocity Modification**:
    *   If the projectile has a `VelocityComponent`, the script accesses it.
    *   It calculates an offset vector based on the direction and calculated gravity strength.
    *   This offset is added to the projectile's existing velocity, effectively pulling it towards the source of the gravity.

### Example Usage (Conceptual)

This script would typically be attached to a special projectile or an entity that emits a gravitational field. When this entity is active, any other projectiles nearby will be influenced by its gravity.

```lua
-- Example of how this script might be triggered or attached
-- This is illustrative and not part of the provided script itself.

-- In another script or entity definition:
-- EntityLoad( "data/entities/special_gravity_emitter.xml" )

-- In special_gravity_emitter.xml:
-- <Entity tags="projectile,gravity_source">
--     <LuaComponent
--         script_path="data/scripts/projectiles/projectile_gravity.lua"
--         execute_every_frame="1"
--     />
--     ... other components ...
-- </Entity>
```