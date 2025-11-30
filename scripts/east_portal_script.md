---
title: East Portal Script
category: scripts
---

# East Portal Script

This script defines the behavior for a portal that teleports the player to the east side of the world. It dynamically adjusts the target Y-coordinate based on the player's current Y-position to ensure they arrive at the appropriate height within the corresponding biome.

## Key Functionality

*   **Teleportation Target:** Sets the destination for the `TeleportComponent`.
*   **Biome-Specific Height Adjustment:** Calculates the correct Y-coordinate based on the player's current Y-position to align with the start of different biomes.
*   **Initial State Management:** Ensures the teleporter is disabled until initialized by the script.

## Core Logic

The script first retrieves the entity's ID and current transform. It then accesses the `TeleportComponent`. The primary X-coordinate for the east biomes is set to `36030`.

The script then uses a series of `if-elseif-else` statements to determine the correct Y-coordinate based on the player's current `pos_y`:

*   **`pos_y < 1200` (Coal Mine or Surface):** `pos_x` is adjusted by `780`, and `pos_y` is set to `0`.
*   **`pos_y < 2732` (Excavation Site):** `pos_y` is set to `1525`.
*   **`pos_y < 4790` (Snow Cave):** `pos_y` is set to `3070`.
*   **`pos_y < 6320` (Snow Castle):** `pos_y` is set to `5118`.
*   **`pos_y < 9368` (Jungle):** `pos_y` is set to `6644`.
*   **`pos_y < 10414` (Vault):** `pos_y` is set to `8704`.
*   **`else` (Deeper):** `pos_y` is set to `10740` (beginning of the Crypt).

Finally, the `target` property of the `TeleportComponent` is updated with the calculated `pos_x` and `pos_y`. The script also ensures the teleporter is enabled only after this initialization by setting components with the tag `"enabled_by_script"` to `true`.

## Key Components and Attributes

*   **`TeleportComponent`**: The core component responsible for handling teleportation.
    *   `target`: A `x, y` coordinate pair defining the destination.
*   **`EntityGetTransform( entity_id )`**: Retrieves the current position of the entity.
*   **`ComponentSetValue2( component, property, value1, value2 )`**: Sets a value for a specific component property.
*   **`EntitySetComponentsWithTagEnabled( entity_id, tag, enabled )`**: Manages the enabled state of components based on their tags.