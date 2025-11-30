---
title: Debug Item Pickup Script
category: scripts
---

# Debug Item Pickup Script

This script defines the `item_pickup` function, which is triggered when an item is picked up by an entity. It's primarily used for debugging purposes and currently implements a single effect: increasing the `max_hp` of the entity that picks up the item.

## Key Function: `item_pickup`

This function handles the logic executed when an item is collected.

### Parameters

*   `entity_item`: The entity representing the item being picked up.
*   `entity_who_picked`: The entity that is picking up the item.
*   `name`: The internal name of the item being picked up.

### Core Logic

1.  **Logging:** Prints "ITEM PICKUP" to the console for debugging.
2.  **Damage Component Check:**
    *   Retrieves all `DamageModelComponent` components attached to the `entity_who_picked`.
    *   If `DamageModelComponent`s are found, it iterates through them.
3.  **HP Increase:**
    *   For each `DamageModelComponent`, it reads the current `max_hp`.
    *   Increments `max_hp` by 1.
    *   Sets the updated `max_hp` back to the component.
4.  **Item Removal:** The `entity_item` is destroyed (removed from the game).

### Example Usage (Conceptual)

While this script is for debugging, a typical scenario would involve an item entity with this script attached. When a player entity collides with it and the pickup logic is triggered, the player's maximum health would increase.

```lua
-- This is a simplified representation of how the script might be used.
-- The actual item pickup trigger is handled by Noita's game engine.

-- Assume 'player_entity' is the entity that picked up the item
-- Assume 'debug_health_item' is the entity representing the item

-- When the player picks up the item:
item_pickup( debug_health_item, player_entity, "debug_health_upgrade" )
```

### Relevant Components

*   **`DamageModelComponent`**: This component is crucial as it holds the health-related properties of an entity. The script directly interacts with its `max_hp` attribute.

### Notes

*   The commented-out line `-- if( hp > max_hp ) then hp = max_hp end` suggests a potential future or alternative implementation where current HP might be capped by the new max HP.
*   This script is a basic example and can be expanded to include various effects based on the `name` of the item picked up.