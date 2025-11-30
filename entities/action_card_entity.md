---
title: Action Card Entity
category: entities
---

# Action Card Entity

This document describes the `action.xml` entity, which serves as a base for custom action cards in Noita. It defines the fundamental components and behaviors for these interactive items.

## Core Components

The `action.xml` entity utilizes several key components to define its properties and interactions:

### ItemComponent
Manages the item's behavior within the game world and inventory.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `_tags`             | `enabled_in_world`: Ensures the component is active when the entity is in the game. |
| `play_spinning_animation` | `0`: Disables a spinning animation for the item.                            |
| `preferred_inventory` | `FULL`: Indicates this item is intended for the main inventory slots.       |

### HitboxComponent
Defines the physical collision area of the entity.

| Attribute   | Description                                                                 |
| :---------- | :-------------------------------------------------------------------------- |
| `_tags`     | `enabled_in_world`: Ensures the hitbox is active in the game.                |
| `aabb_min_x` | `-4`: Minimum X-coordinate of the Axis-Aligned Bounding Box.                |
| `aabb_max_x` | `4`: Maximum X-coordinate of the Axis-Aligned Bounding Box.                 |
| `aabb_min_y` | `-3`: Minimum Y-coordinate of the Axis-Aligned Bounding Box.                |
| `aabb_max_y` | `3`: Maximum Y-coordinate of the Axis-Aligned Bounding Box.                 |

### SimplePhysicsComponent
Applies basic physics to the entity, allowing it to interact with the environment.

| Attribute | Description                                                                 |
| :-------- | :-------------------------------------------------------------------------- |
| `_tags`   | `enabled_in_world`: Ensures physics are active in the game.                  |

### VelocityComponent
Manages the entity's velocity and movement.

| Attribute | Description                                                                 |
| :-------- | :-------------------------------------------------------------------------- |
| `_tags`   | `enabled_in_world`: Ensures velocity is active in the game.                  |

### ItemActionComponent
This is a crucial component for defining the specific action associated with the card.

| Attribute  | Description                                                                 |
| :--------- | :-------------------------------------------------------------------------- |
| `_tags`    | `enabled_in_world`: Ensures the action component is active in the game.      |
| `action_id` | An empty string `""` by default. This should be set to the specific action ID for the custom card. |

## Visual Representation (SpriteComponents)

The entity uses multiple `SpriteComponent`s to manage its visual appearance, often based on its state (e.g., identified, unidentified, background).

### Identified State Sprite
Displayed when the card is identified.

| Attribute     | Description                                                                 |
| :------------ | :-------------------------------------------------------------------------- |
| `_tags`       | `enabled_in_world`, `item_identified`: Active when identified and in-world.  |
| `image_file`  | `data/ui_gfx/gun_actions/empty.png`: The sprite for an identified card.     |
| `offset_x`    | `8`: Horizontal offset for the sprite.                                      |
| `offset_y`    | `17`: Vertical offset for the sprite.                                       |
| `z_index`     | `-1.51`: Controls the layering of the sprite.                               |

### Unidentified State Sprite
Displayed when the card is not yet identified.

| Attribute     | Description                                                                 |
| :------------ | :-------------------------------------------------------------------------- |
| `_enabled`    | `0`: This sprite is disabled by default.                                    |
| `_tags`       | `enabled_in_world`, `item_unidentified`: Active when unidentified and in-world. |
| `image_file`  | `data/ui_gfx/gun_actions/unidentified.png`: The sprite for an unidentified card. |
| `offset_x`    | `8`: Horizontal offset for the sprite.                                      |
| `offset_y`    | `17`: Vertical offset for the sprite.                                       |
| `z_index`     | `-1.51`: Controls the layering of the sprite.                               |

### Inventory Background Sprite
Provides a visual background for the item in the inventory.

| Attribute     | Description                                                                 |
| :------------ | :-------------------------------------------------------------------------- |
| `_enabled`    | `0`: This sprite is disabled by default.                                    |
| `_tags`       | `enabled_in_world`, `item_bg`: Active when it's an inventory background and in-world. |
| `image_file`  | `data/ui_gfx/inventory/item_bg_projectile.png`: The background sprite.      |
| `offset_x`    | `10`: Horizontal offset for the sprite.                                     |
| `offset_y`    | `19`: Vertical offset for the sprite.                                       |
| `z_index`     | `-1.5`: Controls the layering of the sprite.                                |

## Animation (SpriteOffsetAnimatorComponent)

This component adds a subtle vertical bobbing animation to the sprites.

| Attribute   | Description                                                                 |
| :---------- | :-------------------------------------------------------------------------- |
| `_tags`     | `enabled_in_world`: Ensures the animation is active in the game.              |
| `y_amount`  | `1`: The maximum vertical displacement of the animation.                    |
| `y_speed`   | `2.5`: The speed at which the animation plays.                              |
| `sprite_id` | `0`, `1`, `2`, `3`: Applies the animation to specific sprites (likely the visual representations of the card). |