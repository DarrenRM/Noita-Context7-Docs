---
title: Snow Crystal Entity
category: entities
---

# Snow Crystal Entity

This document details the `snowcrystal.xml` entity, which defines the behavior and appearance of the Snow Crystal in Noita.

## Core Attributes

*   **name**: `$animal_snowcrystal` - Internal identifier for the entity.
*   **tags**: `hittable`, `mortal`, `glue_NOT` - Defines its interaction properties. `hittable` and `mortal` indicate it can be damaged and will die. `glue_NOT` suggests it cannot be glued.

## DamageModelComponent

This component governs how the Snow Crystal takes damage and its physical properties when damaged.

*   **hp**: `20` - The total health points of the Snow Crystal.
*   **fire_damage_amount**: `0.2` - The amount of damage taken from fire per tick.
*   **fire_probability_of_ignition**: `0.0` - It cannot be ignited by fire.
*   **blood_material**: `sand_blue` - The material that appears when it's damaged.
*   **materials_damage**: `1` - Indicates that materials can damage it.
*   **ragdoll_material**: `ice_b2` - The material used for its ragdoll when destroyed.
*   **ragdoll_offset_y**: `-6` - Vertical offset for the ragdoll.

### Damage Multipliers

These values specify how much damage the Snow Crystal takes from different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `fire`      | `1.2`      |
| `ice`       | `0.0`      |
| `drill`     | `1.2`      |
| `slice`     | `0.4`      |
| `melee`     | `0.3`      |
| `projectile`| `0.5`      |
| `explosion` | `0.5`      |
| `electricity`| `1.0`      |

## GenomeDataComponent

This component relates to the entity's place within the game's ecosystem and AI.

*   **food_chain_rank**: `20` - Its position in the food chain.
*   **herd_id**: `ghost` - Identifies its group or type for AI purposes.
*   **is_predator**: `1` - Indicates it acts as a predator.

## HitboxComponent

Defines the collision area for the Snow Crystal.

*   **aabb_max_x**: `6`, **aabb_max_y**: `0` - Maximum X and Y coordinates of the bounding box.
*   **aabb_min_x**: `-6`, **aabb_min_y**: `-20` - Minimum X and Y coordinates of the bounding box.
*   **is_enemy**: `0`, **is_item**: `0`, **is_player**: `1` - These flags are unusual. `is_player="1"` might be a placeholder or indicate a specific interaction logic.

## SpriteComponent

Controls the visual representation of the Snow Crystal.

*   **image_file**: `data/buildings_gfx/snowcrystal.xml` - Path to the graphical definition.
*   **rect_animation**: `stand` - The default animation state.

## LightComponent

Adds a light source to the entity.

*   **radius**: `96` - The range of the light.
*   **fade_out_time**: `1.5` - How long the light takes to fade.
*   **r**: `230`, **g**: `120`, **b**: `230` - RGB color values for the light (a purplish hue).
*   **offset_y**: `-6` - Vertical offset for the light source.

## LuaComponent

Links the entity to its custom scripting logic.

*   **script_source_file**: `data/scripts/buildings/snowcrystal.lua` - The Lua script that defines its dynamic behavior.
*   **execute_every_n_frame**: `500` - The script will execute approximately every 500 frames.