---
title: Ghost Crystal Entity
category: entities
---

# Ghost Crystal Entity

This document details the `ghost_crystal.xml` entity, a building-type entity in Noita. It primarily focuses on its visual representation, damage properties, and the scripts that govern its behavior.

## Key Components

### DamageModelComponent

This component defines the health and damage-related properties of the Ghost Crystal.

| Attribute              | Description                                                                 |
| :--------------------- | :-------------------------------------------------------------------------- |
| `hp`                   | Hit points of the entity.                                                   |
| `fire_damage_amount`   | The amount of damage taken from fire per tick.                              |
| `fire_probability_of_ignition` | Probability of igniting when exposed to fire.                               |
| `blood_material`       | The material that spawns when the entity takes damage (e.g., `sand_blue`). |
| `materials_damage`     | Whether materials can damage this entity.                                   |
| `ragdoll_material`     | The material used for the ragdoll when the entity is destroyed.             |

### GenomeDataComponent

This component relates to the entity's place in the game's ecosystem.

| Attribute        | Description                                       |
| :--------------- | :------------------------------------------------ |
| `food_chain_rank`| Its position in the food chain.                   |
| `herd_id`        | Identifier for its group or type (e.g., `ghost`). |
| `is_predator`    | Whether this entity is considered a predator.     |

### HitboxComponent

Defines the collision boundaries of the entity.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `aabb_max_x`| Maximum X-coordinate of the bounding box.                                |
| `aabb_max_y`| Maximum Y-coordinate of the bounding box.                                |
| `aabb_min_x`| Minimum X-coordinate of the bounding box.                                |
| `aabb_min_y`| Minimum Y-coordinate of the bounding box.                                |
| `is_player` | Indicates if this hitbox is associated with the player (likely for interaction). |

### SpriteComponent

Manages the visual appearance and animations of the entity.

| Attribute         | Description                                                              |
| :---------------- | :----------------------------------------------------------------------- |
| `image_file`      | Path to the sprite's image definition file.                              |
| `rect_animation`  | The name of the current rectangle animation (e.g., `stand`).             |
| `offset_x`, `offset_y` | Offsets for positioning the sprite.                                      |

### LightComponent

Adds a light source to the entity.

| Attribute     | Description                                                              |
| :------------ | :----------------------------------------------------------------------- |
| `radius`      | The radius of the light emitted.                                         |
| `fade_out_time`| How long it takes for the light to fade out.                             |
| `r`, `g`, `b` | RGB values defining the color of the light.                              |
| `offset_y`    | Vertical offset for the light source.                                    |

### LuaComponent

These components attach Lua scripts to the entity, defining its dynamic behavior.

| Attribute             | Description                                                                                             |
| :-------------------- | :------------------------------------------------------------------------------------------------------ |
| `script_source_file`  | Path to the Lua script executed when the entity is added.                                               |
| `script_death`        | Path to the Lua script executed when the entity is destroyed.                                           |
| `execute_on_added`    | If `1`, the `script_source_file` will execute once when the entity is added.                            |
| `remove_after_executed`| If `1`, the Lua component is removed after its script has executed.                                     |
| `execute_every_n_frame`| If set to a positive integer, the script will execute every `n` frames. `-1` means not to execute repeatedly. |

### VariableStorageComponent

Allows the entity to store and manage variables.

| Attribute | Description                                                              |
| :-------- | :----------------------------------------------------------------------- |
| `name`    | The name of the variable being stored.                                   |
| `value_int`| The integer value of the variable.                                       |
| `_tags`   | Tags associated with this variable storage (e.g., `ghost_id`).           |

## Summary

The `ghost_crystal.xml` entity is a visually distinct building with moderate health. It emits a colored light and is governed by specific Lua scripts for its unique behaviors, including actions upon being added and upon death. Its hitbox is configured to interact with the player, and it has a defined place within the game's ecosystem.