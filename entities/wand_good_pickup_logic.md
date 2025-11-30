---
title: Wand Good Pickup Logic
category: entities
---

# Wand Good Pickup Logic

This script defines the behavior when a "good" wand is picked up by the player. Its primary function is to manage the existence of other "good" wands in the world.

## Key Functionality

### `item_pickup` Function

This function is called when an item is picked up.

*   **Parameter `entity_item`**: The entity ID of the item being picked up (the wand).
*   **Parameter `entity_who_picked`**: The entity ID of the entity that picked up the item (usually the player).
*   **Parameter `item_name`**: The internal name of the item being picked up.

### "Good" Wand Management

When a "good" wand is picked up:

1.  **Find Existing "Good" Wands**: The script searches for all entities tagged with `"wand_good"`.
2.  **Remove Other "Good" Wands**: If other "good" wands exist in the world (i.e., they have a `VelocityComponent`, indicating they are not just data entities), they are:
    *   Killed (`EntityKill`).
    *   Replaced with a pink poof particle effect (`data/entities/particles/poof_pink.xml`).
    *   This ensures only one "good" wand can be actively present in the world at a time.
3.  **Remove "wand_good" Tag**: The tag `"wand_good"` is removed from the picked-up wand itself to prevent it from being targeted by this logic in the future.
4.  **Spawn Wand Effect**: A special wand effect particle (`data/entities/particles/image_emitters/wand_effect.xml`) is spawned at the location where the wand was picked up.

## Important Considerations

*   **Uniqueness**: The core mechanic is to enforce the presence of only one "good" wand at any given time.
*   **World Presence**: The script checks for `VelocityComponent` to distinguish between wands actively in the game world and those that might be part of data structures.
*   **Visual Feedback**: The poof and wand effect particles provide visual cues for the player.