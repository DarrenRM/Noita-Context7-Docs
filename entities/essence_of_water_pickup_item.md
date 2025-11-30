---
title: Essence of Water Pickup Item
category: entities
---

# Essence of Water Pickup Item

This document describes the `essence_water.xml` entity, which represents the "Essence of Water" pickup item in Noita. This item is a collectible that can be picked up by the player.

## Key Components and Attributes

The `essence_water.xml` entity is composed of several components that define its behavior and appearance.

### `ItemComponent`

This component defines the item's properties as a collectible.

*   **`item_name`**: `$item_essence_water` - The internal name for the item, used for localization.
*   **`ui_description`**: `$itemdesc_essence_water` - The internal name for the item's description, used for localization.
*   **`play_spinning_animation`**: `0` - Disables a spinning animation when the item is on the ground.
*   **`stats_count_as_item_pick_up`**: `0` - This item does not count towards the player's item pickup statistics.

### `SpriteComponent`

This component handles the visual representation of the item.

*   **`image_file`**: `data/items_gfx/essences/essence_water.png` - Specifies the texture file for the item's sprite.
*   **`offset_x`**: `8` - Adjusts the horizontal position of the sprite.
*   **`offset_y`**: `8` - Adjusts the vertical position of the sprite.
*   **`update_transform`**: `1` - Enables the sprite to update its position based on the entity's transform.
*   **`update_transform_rotation`**: `0` - Disables the sprite from rotating with the entity's transform.

### `VariableStorageComponent`

This component stores custom variables associated with the entity.

*   **`name`**: `essence_id` - The name of the variable.
*   **`value_string`**: `water` - The string value assigned to the `essence_id` variable, identifying this as the "water" essence.

### `LuaComponent`

This component allows for custom Lua scripting to be attached to the entity.

*   **`script_item_picked_up`**: `data/scripts/essences/essence_pickup.lua` - Specifies the Lua script to be executed when the item is picked up by the player. This script likely handles the logic for what happens when the player collects this essence.