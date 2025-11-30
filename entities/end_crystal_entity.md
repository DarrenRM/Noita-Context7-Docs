---
title: End Crystal Entity
category: entities
---

# End Crystal Entity

This document describes the `endcrystal` entity, a unique building in Noita. It primarily serves as a visual element with a light source and is associated with a specific script for its behavior when picked up.

## Key Components

### SpriteComponent
This component defines the visual appearance of the End Crystal.

| Attribute       | Value                               | Description                                                                 |
| :-------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `image_file`    | `data/buildings_gfx/endcrystal.xml` | Specifies the graphical asset file for the crystal's sprite.                |
| `rect_animation`| `stand`                             | The default animation state for the sprite.                                 |
| `has_special_scale` | `1`                             | Indicates that the sprite might have custom scaling applied.                |
| `alpha`         | `1`                                 | Full opacity for the sprite.                                                |
| `offset_x`, `offset_y` | `0`                             | No offset from the entity's origin.                                         |

### LightComponent
This component adds a light source emanating from the End Crystal.

| Attribute     | Value   | Description                                                                 |
| :------------ | :------ | :-------------------------------------------------------------------------- |
| `radius`      | `96`    | The radius of the light emitted.                                            |
| `fade_out_time` | `1.5`   | The time it takes for the light to fade out.                                |
| `r`, `g`, `b` | `230`, `120`, `230` | The RGB color values for the light, creating a purplish hue.              |

### ItemComponent
This component marks the entity as an item that can be picked up.

| Attribute           | Value | Description                                                                 |
| :------------------ | :---- | :-------------------------------------------------------------------------- |
| `item_name`         | `Mystical Crystal Ball` | The display name of the item when it's in the inventory or world.           |
| `play_hover_animation` | `1`   | Enables a hovering animation for the item when it's picked up or on the ground. |

### LuaComponent
This component links the entity to a Lua script that defines its behavior.

| Attribute             | Value                                | Description                                                                 |
| :-------------------- | :----------------------------------- | :-------------------------------------------------------------------------- |
| `script_item_picked_up` | `data/scripts/buildings/endcrystal.lua` | The script executed when the item is picked up by the player.               |

### HitboxComponent
Defines the collision area for the entity, particularly relevant for interaction and physics.

| Attribute     | Value   | Description                                                                 |
| :------------ | :------ | :-------------------------------------------------------------------------- |
| `aabb_min_x`  | `-256`  | Minimum X-coordinate of the Axis-Aligned Bounding Box.                      |
| `aabb_max_x`  | `256`   | Maximum X-coordinate of the Axis-Aligned Bounding Box.                      |
| `aabb_min_y`  | `-320`  | Minimum Y-coordinate of the Axis-Aligned Bounding Box.                      |
| `aabb_max_y`  | `206`   | Maximum Y-coordinate of the Axis-Aligned Bounding Box.                      |

## Other Components

*   **`VelocityComponent`**: Present, but likely has no default velocity.
*   **`SimplePhysicsComponent`**: Indicates the entity participates in basic physics simulations.
*   **`Entity tags="workshop,workshop_show_hint"`**: This entity is tagged for inclusion in the workshop and to display hints related to it.