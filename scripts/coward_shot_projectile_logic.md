---
title: Coward Shot Projectile Logic
category: scripts
---

---

# Coward Shot Projectile Logic

This script defines the behavior for a projectile that attempts to home in on a specific target. It prioritizes targets with a high herd relation to the projectile's owner.

## Key Functionality

*   **Target Acquisition:** The projectile searches for entities within a radius that have the "homing_target" tag.
*   **Target Selection:** It randomly selects a potential target from the found entities.
*   **Target Validation:** The selected target is validated to ensure it's not the projectile itself or its owner, and that it has a herd relation of at least 40 with the owner.
*   **Effect Application:** If a valid target is found, a "tinyspark_green_trail" particle effect is spawned at the target's location, tagged as "coward_effect," and attached as a child to the target.
*   **Target Storage:** The ID of the chosen target is stored in a `VariableStorageComponent` named "target" on the projectile.

## Core Attributes & Logic

### Target Search

*   **`radius`**: Defines the search radius for potential targets (currently set to `200`).
*   **`homing_target` tag**: Entities must possess this tag to be considered as potential targets.

### Target Prioritization

*   **`EntityGetHerdRelation( v, owner_id ) >= 40`**: This is the primary condition for selecting a valid target. A higher herd relation value indicates a stronger positive relationship.
*   **Random Selection with Iteration**: The script uses a `while` loop and modulo arithmetic (`j = ( j % #targets ) + 1`) to iterate through potential targets in a randomized order until a valid one is found or all targets have been checked.

### Effect Spawning

*   **`EntityLoad( "data/entities/particles/tinyspark_green_trail.xml", tx, ty )`**: Spawns a specific particle effect at the target's coordinates.
*   **`EntityAddTag( eid, "coward_effect" )`**: Applies a tag to the spawned effect for potential further scripting.
*   **`EntityAddChild( target, eid )`**: Attaches the spawned effect to the target entity, ensuring it moves with the target.

### Target Data Storage

*   **`VariableStorageComponent`**: The script looks for a component of this type on the projectile.
*   **`name == "target"`**: Specifically targets a variable within the `VariableStorageComponent` named "target".
*   **`ComponentSetValue2( v, "value_int", target )`**: Stores the `entity_id` of the chosen target as an integer value.