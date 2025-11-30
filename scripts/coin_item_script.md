---
title: Coin Item Script
category: scripts
---

# Coin Item Script

This script defines the behavior for a coin item in Noita. When picked up, it adds a small amount of money to the player's wallet and then destroys itself.

## Key Functionality

### `item_pickup` Function

This function is called when the coin item is picked up by a player.

*   **Purpose:** To grant the player money and remove the coin from the game.
*   **Parameters:**
    *   `entity_item`: The entity representing the coin item itself.
    *   `entity_who_picked`: The entity that picked up the coin (usually the player).
    *   `name`: The name of the item being picked up.

### Wallet Interaction

The script checks for and interacts with the player's `WalletComponent`.

*   **`EntityGetComponent( entity_who_picked, "WalletComponent" )`**: Retrieves the `WalletComponent` attached to the player entity.
*   **Iteration**: If a `WalletComponent` is found, the script iterates through its contents.
*   **Money Addition**: For each wallet entry, it retrieves the current `money` value, increments it by 1, and updates the component with the new value.
*   **`GamePrint( money )`**: Displays the updated money amount to the player (this might be a debug or legacy print).

### Item Removal

*   **`EntityKill( entity_item )`**: This line ensures that the coin item is removed from the game world after it has been picked up and its effect applied.

## Notes

*   The comment `NOTE( Petri ): 24.4.2024 - this is legacy file?` suggests this script might be an older implementation and could potentially be refactored or replaced in newer versions of the game or mods.