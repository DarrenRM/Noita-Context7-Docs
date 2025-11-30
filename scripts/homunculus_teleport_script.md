---
title: Homunculus Teleport Script
category: scripts
---

---

# Homunculus Teleport Script

This script handles the teleportation logic for a homunculus entity in Noita. When the homunculus is a significant distance from the player, it will teleport to the player's location.

## Functionality

The script performs the following actions:

1.  **Get Entity Information**: Retrieves the current entity ID and its position (`x`, `y`).
2.  **Find Player**: Locates all entities tagged as "player\_unit".
3.  **Distance Check**: If a player is found, it calculates the Manhattan distance (`d`) between the homunculus and the player.
4.  **Teleportation Trigger**: If the distance `d` is greater than 180 units:
    *   **Visual Effects**: Loads `teleportation_source.xml` particle effect at the homunculus's current location.
    *   **Visual Effects**: Loads `teleportation_target.xml` particle effect at the player's location.
    *   **Position Update**: Moves the homunculus entity to the player's position (`px`, `py`).

## Key Attributes/Elements

*   **`entity_id`**: The unique identifier for the homunculus entity.
*   **`x`, `y`**: The current world coordinates of the homunculus.
*   **`players`**: A table containing all entities with the "player\_unit" tag.
*   **`p`**: The first player entity found in the `players` table.
*   **`px`, `py`**: The world coordinates of the player.
*   **`d`**: The calculated Manhattan distance between the homunculus and the player.
*   **`180`**: The distance threshold (in units) that triggers the teleportation.
*   **`EntityLoad("data/entities/particles/teleportation_source.xml", x, y)`**: Spawns a particle effect indicating the teleportation origin.
*   **`EntityLoad("data/entities/particles/teleportation_target.xml", px, py)`**: Spawns a particle effect indicating the teleportation destination.
*   **`EntitySetTransform(entity_id, px, py)`**: Updates the homunculus's position to the player's location.