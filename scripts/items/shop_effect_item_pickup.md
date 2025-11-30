---
title: Shop Effect Item Pickup
category: scripts/items
---

# Shop Effect Item Pickup

This script defines the behavior when a specific item, likely related to shop effects, is picked up by the player.

## `item_pickup` Function

This is the primary function executed when the item is collected.

### Parameters

*   `entity_item`: The entity representing the item being picked up.
*   `entity_who_picked`: The entity that picked up the item (usually the player).
*   `name`: The internal name of the item.

### Behavior

1.  **Get Item Position**: It retrieves the `x` and `y` coordinates of the `entity_item`.
2.  **Spawn Shop Effect Particle**: It loads and spawns a particle entity named `shop_effect.xml` from `data/entities/particles/image_emitters/`. This particle is positioned slightly above the item's location (`y-8`).

### Key Elements

*   **`EntityLoad`**: This is the core function responsible for instantiating new entities within the game world.
*   **`data/entities/particles/image_emitters/shop_effect.xml`**: This path indicates the specific particle effect that is triggered. This XML file would contain the visual and behavioral definitions for the shop effect.
*   **Positioning**: The `x, y-8` argument ensures the particle effect appears visually connected to the item pickup.