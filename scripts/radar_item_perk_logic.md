---
title: Radar Item Perk Logic
category: scripts
---

# Radar Item Perk Logic

This script defines the functionality for a perk that visually indicates the presence of nearby wands. It pings the location of dropped wands within a specified radius, with the visual intensity of the ping varying based on proximity.

## Core Functionality

The script iterates through entities tagged with "item_pickup" within a defined radius around the player. For each identified item, it checks if it's a wand and not owned by the player. If these conditions are met, it calculates the direction and distance to the wand and spawns a visual indicator sprite.

### Key Attributes and Elements

*   **`entity_id`**: The unique identifier for the entity executing this script (presumably the player with the perk).
*   **`pos_x`, `pos_y`**: The player's current X and Y coordinates.
*   **`range`**: The maximum distance (in pixels) within which the perk will detect items. Set to `400`.
*   **`indicator_distance`**: The distance from the player at which the indicator sprites will be spawned. Set to `22`.
*   **`EntityGetInRadiusWithTag(pos_x, pos_y, range, "item_pickup")`**: This function finds all entities within the specified radius that have the "item\_pickup" tag.
*   **`IsPlayer(parent)`**: A check to ensure the detected item is not a wand the player is currently holding or interacting with.
*   **`get_magnitude(dir_x, dir_y)`**: Calculates the distance between the player and the detected wand.
*   **`vec_normalize(dir_x, dir_y)`**: Normalizes the direction vector to a unit vector, used for positioning the indicator.
*   **`GameCreateSpriteForXFrames(sprite_path, x, y)`**: Spawns a sprite at the given coordinates. The sprite used depends on the distance to the wand:
    *   `data/particles/radar_item_faint.png`: For wands further than 50% of the `range`.
    *   `data/particles/radar_item_medium.png`: For wands between 25% and 50% of the `range`.
    *   `data/particles/radar_item_strong.png`: For wands within 25% of the `range` (and further than 10 pixels).

### Logic Flow

1.  Get the player's entity ID and position.
2.  Define the detection `range` and `indicator_distance`.
3.  Loop through all entities tagged "item\_pickup" within the `range`.
4.  For each entity, get its transform and parent.
5.  If the entity is not owned by the player:
    *   Calculate the direction and distance to the entity.
    *   Normalize the direction vector.
    *   Calculate the position for the indicator sprite.
    *   Based on the `distance`, choose and spawn the appropriate indicator sprite (`faint`, `medium`, or `strong`).