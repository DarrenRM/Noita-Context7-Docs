---
title: Spell Refresh Item Script
category: scripts
---

# Spell Refresh Item Script

This script defines the behavior for the "Spell Refresh" item in Noita. When picked up, it triggers a visual effect, displays a message to the player, and regenerates the player's spell actions. The item itself is then removed from the game.

## Key Functions

### `item_pickup( entity_item, entity_who_picked, name )`

This function is called when the "Spell Refresh" item is picked up by a player.

*   **`entity_item`**: The entity representing the item being picked up.
*   **`entity_who_picked`**: The entity representing the player who picked up the item.
*   **`name`**: The internal name of the item (e.g., "spell\_refresh").

#### Core Logic:

1.  **Get Item Position**: Retrieves the `x` and `y` coordinates of the `entity_item`.
2.  **Spawn Visual Effect**: Loads and spawns `data/entities/particles/image_emitters/spell_refresh_effect.xml` at a position slightly above the item's location.
3.  **Display Message**: Uses `GamePrintImportant` to show the item's title (`$itemtitle_spell_refresh`) and description (`$itemdesc_spell_refresh`) to the player.
4.  **Regenerate Spell Actions**: Calls `GameRegenItemActionsInPlayer` on the `entity_who_picked` to refresh the player's available spell slots.
5.  **Remove Item**: Destroys the `entity_item` using `EntityKill`.

## Dependencies

*   `data/scripts/game_helpers.lua`: Provides utility functions for game operations.
*   `data/entities/particles/image_emitters/spell_refresh_effect.xml`: The visual effect spawned upon pickup.