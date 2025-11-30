---
title: Full HP Heart Item Script
category: scripts
---

# Full HP Heart Item Script

This script defines the behavior for the "Full HP Heart" item in Noita. When picked up, it fully restores the player's health and plays a visual effect.

## Core Functionality

The `item_pickup` function is the primary logic for this item.

### `item_pickup( entity_item, entity_who_picked, name )`

This function is called when the item is picked up by a player.

*   **`entity_item`**: The entity representing the heart item itself.
*   **`entity_who_picked`**: The entity of the player who picked up the item.
*   **`name`**: The internal name of the item (e.g., "data/entities/items/heart_fullhp.xml").

### Key Actions:

1.  **Health Restoration**:
    *   It iterates through the `DamageModelComponent` of the player entity.
    *   It retrieves the `max_hp` and current `hp`.
    *   It calculates the `healing` amount (difference between `max_hp` and current `hp`).
    *   It sets the player's current `hp` to `max_hp`, effectively healing them completely.

2.  **Visual Effects**:
    *   `EntityLoad("data/entities/particles/image_emitters/heart_fullhp_effect.xml", x, y-12)`: Spawns a visual effect related to the full HP restoration.
    *   `EntityLoad("data/entities/particles/heart_out.xml", x, y-8)`: Spawns a particle effect indicating the item's consumption.

3.  **Game Log Notification**:
    *   `GamePrintImportant(...)`: Displays an important message in the game log, indicating the amount of health restored. The message uses localized strings (`$log_heart_fullhp`, `$logdesc_heart_fullhp`) and includes the calculated healing amount.

4.  **Item Removal**:
    *   `EntityKill( entity_item )`: Removes the heart item from the game world after it has been picked up and its effects applied.

## Important Attributes/Components Involved

*   **`DamageModelComponent`**: This component is crucial for managing health-related attributes of entities. The script specifically targets this component to read `max_hp` and `hp`, and to set the `hp` value.
*   **`EntityTransform`**: Used to get the position (`x`, `y`) of the item for spawning effects.
*   **`ComponentGetValue` / `ComponentSetValue`**: Standard functions for interacting with entity components.
*   **`EntityLoad`**: Used to spawn particle and effect entities.
*   **`GamePrintImportant` / `GameTextGet`**: Functions for displaying in-game messages and retrieving localized text.
*   **`EntityKill`**: Used to remove entities from the game.