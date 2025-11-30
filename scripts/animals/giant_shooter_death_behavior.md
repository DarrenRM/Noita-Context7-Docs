---
title: Giant Shooter Death Behavior
category: scripts/animals
---

# Giant Shooter Death Behavior

This script defines the behavior of a Giant Shooter entity when it receives damage, specifically focusing on its death sequence.

## Key Functionality

The primary function `damage_received` is triggered when the Giant Shooter takes damage. It checks the remaining health and, under specific conditions, spawns smaller "slimeshooter" entities.

### `damage_received( damage, desc, entity_who_caused, is_fatal )`

This function handles the logic executed when the Giant Shooter entity's health is reduced.

*   **`damage`**: The amount of damage received.
*   **`desc`**: A description of the damage source (not directly used in this script).
*   **`entity_who_caused`**: The entity that inflicted the damage (not directly used).
*   **`is_fatal`**: A boolean indicating if the damage is fatal (not directly used).

#### Core Logic:

1.  **Get Entity Information**: Retrieves the current entity ID and its world coordinates (`x`, `y`).
2.  **Random Seed**: Initializes a random seed based on game frame number and entity position for consistent randomness within the death event.
3.  **Health Check**:
    *   It retrieves the current health of the Giant Shooter.
    *   It checks if the health is above 0.3 and will drop below 0.3 after the current damage is applied. This threshold determines when the spawning behavior is triggered.
4.  **Spawn Slimeshooters**:
    *   If the health condition is met, the script enters a loop to spawn three smaller "slimeshooter" entities.
    *   Each slimeshooter is spawned at a slightly randomized position relative to the Giant Shooter's death location.
    *   **`EntityLoad( "data/entities/animals/slimeshooter.xml", x + offsetx, y + offsety )`**: This line loads the `slimeshooter.xml` entity.
5.  **Slimeshooter Velocity**:
    *   After spawning a slimeshooter, its `VelocityComponent` is edited to give it a randomized velocity.
    *   **`ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y )`**: Sets the velocity with `vel_x` ranging from -90 to 90 and `vel_y` ranging from -150 to 25, giving them a slight upward and horizontal push.

## Key Attributes/Elements

*   **`edit_component`**: Used to access and modify components of an entity.
*   **`ComponentGetValue`**: Retrieves the value of a component's field (e.g., `hp`).
*   **`ComponentSetValueVector2`**: Sets a 2D vector value for a component's field (e.g., `mVelocity`).
*   **`EntityLoad`**: Spawns a new entity in the game world.
*   **`Random`**: Generates a random number within a specified range.
*   **`GetUpdatedEntityID`**: Gets the ID of the entity currently being processed.
*   **`SetRandomSeed`**: Sets the seed for the random number generator.
*   **`GameGetFrameNum`**: Gets the current game frame number.

## Summary

This script implements a "death explosion" effect for the Giant Shooter, where it breaks apart into smaller, independently moving slimeshooters when its health reaches a critical low point. This adds a dynamic and challenging element to its demise.