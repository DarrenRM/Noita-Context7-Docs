---
title: Base Shop Item Entity
category: entities
---

# Base Shop Item Entity

This XML defines the fundamental structure for shop items in Noita. It serves as a template for other shop item entities, providing essential components for their functionality and appearance within the game's shop system.

## Key Components

### `ItemCostComponent`

This component dictates the cost of the item in the shop.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `cost`    | The price of the item in gold.            |

### `SpriteComponent`

This component handles the visual representation of the item's cost displayed in the shop.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `_tags`             | Tags applied to the sprite, including `shop_cost` and `enabled_in_world`. |
| `image_file`        | The image file used for the sprite (often a font file for text).            |
| `is_text_sprite`    | A flag indicating if the sprite is text-based.                              |
| `offset_x`, `offset_y` | Adjusts the horizontal and vertical position of the sprite.                 |
| `update_transform`  | Enables or disables transform updates for the sprite.                       |
| `text`              | The actual text to be displayed (e.g., the item's cost).                    |
| `z_index`           | Controls the layering of the sprite.                                        |

## Entity Tags

The `Entity` itself has several important tags:

*   `hittable`: Indicates the item can be interacted with via damage.
*   `item`: Marks it as a collectible item.
*   `item_shop`: Identifies it as a shop-specific item.
*   `glue_NOT`: A tag that prevents certain behaviors, likely related to gluing.