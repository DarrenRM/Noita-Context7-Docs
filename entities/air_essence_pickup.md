---
title: Air Essence Pickup
category: entities
---

---

# Air Essence Pickup

This document describes the Air Essence pickup item in Noita, focusing on its attributes relevant to AI-assisted modding.

## Entity Definition

The Air Essence is an item pickup entity with the following key tags:

*   `teleportable_NOT`: This entity cannot be teleported.
*   `essence`: Identifies it as an essence type item.
*   `item_pickup`: Marks it as an item that can be picked up by the player.

## Key Components

### ItemComponent

This component defines the basic properties of the item.

| Attribute           | Value        | Description                                                                 |
| :------------------ | :----------- | :-------------------------------------------------------------------------- |
| `item_name`         | `$item_essence_air` | The internal name for the item, used for localization.                      |
| `ui_description`    | `$itemdesc_essence_air` | The internal description for the item, used for localization.               |
| `play_spinning_animation` | `0`          | Disables a spinning animation when the item is on the ground.               |
| `stats_count_as_item_pick_up` | `0`          | This item does not count towards the player's total item pickups statistic. |

### SpriteComponent

This component handles the visual representation of the item.

| Attribute      | Value                               | Description                                                              |
| :------------- | :---------------------------------- | :----------------------------------------------------------------------- |
| `image_file`   | `data/items_gfx/essences/essence_air.png` | The path to the sprite image for the Air Essence.                        |
| `offset_x`     | `8`                                 | Horizontal offset for the sprite.                                        |
| `offset_y`     | `8`                                 | Vertical offset for the sprite.                                          |
| `update_transform` | `1`                                 | The sprite's transform (position, rotation, scale) will be updated.      |
| `update_transform_rotation` | `0`                                 | The sprite's rotation will not be updated independently.                 |

### VariableStorageComponent

This component stores custom variables associated with the entity.

| Attribute    | Value   | Description                                                                 |
| :----------- | :------ | :-------------------------------------------------------------------------- |
| `name`       | `essence_id` | The name of the variable.                                                   |
| `value_string` | `air`   | The string value assigned to `essence_id`, identifying it as the "air" essence. |

### LuaComponent

This component links the item to a Lua script for custom behavior.

| Attribute           | Value                                | Description                                                                                             |
| :------------------ | :----------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `script_item_picked_up` | `data/scripts/essences/essence_pickup.lua` | The Lua script executed when the item is picked up by the player. This script likely handles essence collection logic. |