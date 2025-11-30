---
title: Cape Item Entity
category: entities
---

---

# Cape Item Entity

This document describes the Noita entity definition for a Cape item.

## Core Components

This entity utilizes several core Noita components to define its behavior and appearance.

### `UIInfoComponent`

Provides basic information for the item's UI representation.

| Attribute | Value       | Description                               |
| :-------- | :---------- | :---------------------------------------- |
| `name`    | `Cape upgrade` | The name displayed in the UI.             |

### `HitboxComponent`

Defines the physical boundaries of the item.

| Attribute   | Value   | Description                                                              |
| :---------- | :------ | :----------------------------------------------------------------------- |
| `aabb_min_x`| `-6`    | Minimum X-axis extent of the hitbox.                                     |
| `aabb_max_x`| `6`     | Maximum X-axis extent of the hitbox.                                     |
| `aabb_min_y`| `-8`    | Minimum Y-axis extent of the hitbox.                                     |
| `aabb_max_y`| `0`     | Maximum Y-axis extent of the hitbox.                                     |
| `is_item`   | `1`     | Indicates that this entity is an item.                                   |
| `is_player` | `0`     | Indicates that this entity is not the player.                            |

### `ItemComponent`

Specifies item-specific properties.

| Attribute             | Value                | Description                                       |
| :-------------------- | :------------------- | :------------------------------------------------ |
| `item_name`           | `Fire protection cape` | The internal name of the item.                    |
| `play_spinning_animation` | `0`                  | Disables spinning animation when picked up.       |

### `LuaComponent` (Pickup Script)

This component links to a Lua script that executes when the item is picked up.

| Attribute             | Value                                   | Description                                                              |
| :-------------------- | :-------------------------------------- | :----------------------------------------------------------------------- |
| `script_item_picked_up` | `data/scripts/items/protection_cape.lua` | The path to the Lua script executed upon item pickup.                    |

### `VariableStorageComponent`

Stores custom variables associated with the entity.

| Attribute     | Value            | Description                                                              |
| :------------ | :--------------- | :----------------------------------------------------------------------- |
| `name`        | `type`           | The name of the variable.                                                |
| `value_string`| `protection_fire`| The string value assigned to the variable, likely indicating its effect. |

### `LuaComponent` (Initialization Script)

This component executes a Lua script once upon entity initialization.

| Attribute             | Value                                    | Description                                                              |
| :-------------------- | :--------------------------------------- | :----------------------------------------------------------------------- |
| `script_source_file`  | `data/scripts/items/init_random_cape.lua`| The path to the Lua script executed once at initialization.              |
| `remove_after_executed`| `1`                                      | Ensures the script component is removed after its execution.             |

### `LightComponent`

Adds a light source to the entity.

| Attribute      | Value | Description                                                              |
| :------------- | :---- | :----------------------------------------------------------------------- |
| `r`, `g`, `b`  | `255` | Sets the light color to white (RGB values).                              |
| `radius`       | `64`  | The radius of the light emitted.                                         |
| `fade_out_time`| `0.75`| The time it takes for the light to fade out.                             |

### `SpriteComponent`

Defines the visual representation of the item.

| Attribute      | Value                                | Description                                                              |
| :------------- | :----------------------------------- | :----------------------------------------------------------------------- |
| `image_file`   | `data/items_gfx/cape/default.xml`    | The path to the sprite's image file.                                     |
| `offset_x`, `offset_y` | `0`                                  | The horizontal and vertical offset of the sprite.                        |
| `z_index`      | `20`                                 | The rendering order of the sprite. Higher values are drawn on top.       |

## Other Components

The entity also includes:

*   **`VelocityComponent`**: Likely for basic physics simulation.
*   **`SimplePhysicsComponent`**: Further physics properties.