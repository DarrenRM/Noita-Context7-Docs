---
title: Boss Dragon Entity
category: entities
---

# Boss Dragon Entity

This document details the configuration of the Boss Dragon entity in Noita, focusing on its core attributes and components relevant for AI-assisted modding.

## Core Entity Attributes

The `Entity` tag defines the fundamental properties of the Boss Dragon.

*   **`name`**: `$animal_boss_dragon` - The internal identifier for this entity.
*   **`tags`**: `enemy,mortal,hittable,teleportable_NOT,boss_dragon,homing_target,glue_NOT,necrobot_NOT,polymorphable_NOT` - A set of tags that define its behavior and interactions within the game. Key tags include `enemy`, `boss_dragon`, and `homing_target`.

## Key Components

The following components define the Boss Dragon's behavior, appearance, and combat mechanics.

### BossDragonComponent

This component governs the dragon's movement, targeting, and overall boss-like behavior.

*   **`speed`**: `3` - Base movement speed.
*   **`speed_hunt`**: `4` - Movement speed when actively hunting a target.
*   **`acceleration`**: `0.25` - How quickly the dragon reaches its target speed.
*   **`tail_gravity`**: `30` - Influences the physics of its tail segments.
*   **`part_distance`**: `16` - The desired distance between segments of its body.
*   **`hitbox_radius`**: `9` - The radius of the dragon's primary hitbox.
*   **`hunt_box_radius`**: `256` - The radius within which the dragon actively seeks targets.
*   **`random_target_box_radius`**: `400` - The radius for seeking random targets when not actively hunting.
*   **`ragdoll_filename`**: `data/ragdolls/dragon/filenames.txt` - Specifies the ragdoll configuration file.
*   **`jump_cam_shake`**: `20` - The intensity of camera shake when the dragon jumps.

### DamageModelComponent

Manages the dragon's health and how it takes damage.

*   **`hp`**: `120` - The total health points of the Boss Dragon.
*   **`materials_damage`**: `1` - Indicates that the dragon can be damaged by materials.
*   **`materials_how_much_damage`**: `0.1` - The amount of damage taken from specific materials.
*   **`materials_that_damage`**: `acid` - The type of material that inflicts damage.

#### damage_multipliers

Defines how much damage the dragon takes from different damage types.

| Type        | Multiplier |
| :---------- | :--------- |
| `explosion` | `0.5`      |
| `fire`      | `0.5`      |
| `ice`       | `0.5`      |
| `electricity` | `0.3`      |

### GenomeDataComponent

Provides information for the game's ecosystem simulation.

*   **`herd_id`**: `boss_dragon` - Identifies this creature within its herd.
*   **`food_chain_rank`**: `20` - Its position in the food chain.
*   **`is_predator`**: `1` - Indicates that it is a predator.

### SpriteComponent

Multiple `SpriteComponent` instances define the visual appearance of the Boss Dragon.

*   **`image_file`**: Points to the `.xml` files defining the dragon's head, body, and tail graphics (e.g., `data/enemies_gfx/dragon_head.xml`, `data/enemies_gfx/dragon_body.xml`, `data/enemies_gfx/dragon_tail.xml`).
*   **`rect_animation`**: `eat` - Specifies the animation to use.
*   **`offset_x`, `offset_y`**: Adjust the sprite's position relative to the entity's transform.
*   **`update_transform`**: `0` - Indicates that the sprite's transform is not directly updated by the entity's movement.

Two specific `SpriteComponent` instances are used for the health bar UI:

*   **`image_file`**: `data/ui_gfx/health_slider_back.png` and `data/ui_gfx/health_slider_front.png`.
*   **`_tags`**: `health_bar_back,ui,no_hitbox` and `health_bar,ui,no_hitbox`.
*   **`z_index`**: `-9000` - Ensures the health bar is rendered behind other game elements.

### LightComponent

Adds a light source to the entity.

*   **`radius`**: `100` - The range of the light.
*   **`r`, `g`, `b`**: `255, 149, 0` - Defines the light color as orange.

### AudioLoopComponent

Manages ambient sound effects.

*   **`file`**: `data/audio/Desktop/animals.bank` - The audio bank containing the sound event.
*   **`event_name`**: `animals/worm/movement_loop_big` - The specific sound event to play.
*   **`auto_play`**: `1` - The sound starts automatically when the entity is spawned.

### Entity (Nested)

A nested `Entity` block contains specific components for a part of the Boss Dragon, likely related to its projectile or special attack.

*   **`InheritTransformComponent`**: `parent_sprite_id="10"` - Inherits transform from a specific sprite (likely the tail).
*   **`LuaComponent`**:
    *   **`script_source_file`**: `data/scripts/projectiles/orb_green_dragon.lua` - The Lua script controlling its behavior.
    *   **`execute_every_n_frame`**: `80` - How often the script logic is executed.
    *   **`execute_times`**: `-1` - The script runs indefinitely.
*   **`GenomeDataComponent`**: Duplicated here, reinforcing its ecological role.