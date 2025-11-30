---
title: Greed Curse Item Pickup
category: entities
---

# Greed Curse Item Pickup

This entity defines the pickup behavior for the "Greed Curse" item in Noita.

## Entity Definition

The core entity is tagged as `teleportable_NOT`, `essence`, and `item_pickup`, indicating it's an item that can be picked up but not teleported.

## Key Components

### ItemComponent

This component defines the item's properties as recognized by the game's item system.

| Attribute                 | Value                               | Description                                                                 |
| :------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `item_name`               | `$item_essence_greed`               | The internal name for the item, likely linked to localization for display.  |
| `ui_description`          | `$itemdesc_essence_greed`           | The internal description for the item, also linked to localization.         |
| `play_spinning_animation` | `0`                                 | Disables a spinning animation when the item is picked up.                   |
| `stats_count_as_item_pick_up` | `0`                                 | This item does not count towards general item pickup statistics.            |

### SpriteComponent

This component handles the visual representation of the item.

| Attribute      | Value                               | Description                                                                 |
| :------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `image_file`   | `data/items_gfx/greed_curse.png`    | Specifies the image file used for the item's sprite.                      |
| `offset_x`     | `8`                                 | Horizontal offset for the sprite.                                           |
| `offset_y`     | `8`                                 | Vertical offset for the sprite.                                             |
| `update_transform` | `1`                                 | The sprite's transform (position, rotation, scale) should be updated.       |
| `update_transform_rotation` | `0`                                 | The sprite's rotation is not updated independently.                         |

### LuaComponent

This component links the item pickup to a specific Lua script for custom behavior.

| Attribute             | Value                                                | Description                                                                 |
| :-------------------- | :--------------------------------------------------- | :-------------------------------------------------------------------------- |
| `script_item_picked_up` | `data/scripts/magic/greed_curse/greed_curse_pickup.lua` | The Lua script executed when this item is picked up by the player.          |