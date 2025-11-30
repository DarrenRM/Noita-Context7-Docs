---
title: Big Worm Entity
category: entities
---

# Big Worm Entity

This document details the configuration of the "Big Worm" entity in Noita, focusing on its core attributes and AI behavior for modding purposes.

## Core Entity Properties

The `Entity` tag defines the fundamental characteristics of the Big Worm.

*   **`tags`**: `mortal,hittable,teleportable_NOT,homing_target,enemy,worm` - These tags dictate its interactions with the game world, including its ability to be damaged, targeted, and its classification as an enemy worm.
*   **`name`**: `$animal_worm_big` - The internal name for this entity, used for referencing in game files.

## Worm Component

The `WormComponent` governs the physical and movement properties of the worm's body segments.

*   **`acceleration`**: `1.5` - How quickly the worm can change its speed.
*   **`gravity`**: `3` - The gravitational pull affecting the worm's main body.
*   **`tail_gravity`**: `30` - The significantly higher gravitational pull on the worm's tail segments, causing it to sag.
*   **`part_distance`**: `16` - The spacing between individual body segments.
*   **`hitbox_radius`**: `9` - The radius of the collision box for each segment.
*   **`target_kill_radius`**: `10` - The radius within which the worm can "eat" and kill targets.

## Worm AI Component

The `WormAIComponent` controls the worm's decision-making and targeting behavior.

*   **`speed`**: `4` - The base movement speed of the worm.
*   **`speed_hunt`**: `5` - The increased speed when actively hunting a target.
*   **`hunt_box_radius`**: `256` - The radius within which the worm will actively search for targets.
*   **`random_target_box_radius`**: `128` - The radius for seeking random points to move towards when not hunting.
*   **`give_up_time_frames`**: `250` - The number of frames the worm will continue to pursue a target before giving up.

## Damage Model Component

The `DamageModelComponent` defines the worm's health and how it takes damage.

*   **`hp`**: `140` - The total hit points of the Big Worm.
*   **`fire_damage_amount`**: `0.2` - The damage dealt by fire per tick.
*   **`fire_probability_of_ignition`**: `0.5` - The chance of catching fire when hit by fire damage.
*   **`blood_material`**: `blood_worm` - The material used for blood splatters.
*   **`materials_that_damage`**: `acid,lava` - Specific materials that inflict damage on the worm.
*   **`materials_how_much_damage`**: `0.0001,0.0001` - The damage multiplier for the listed materials.
*   **`damage_multipliers`**:
    *   **`drill`**: `0.4` - Reduces damage taken from drills.

## Sprite Components

These components define the visual appearance of the Big Worm, including its head, body, and tail segments. Multiple `SpriteComponent` entries for the body create the segmented look.

*   **`image_file`**: Specifies the graphical asset for each part (e.g., `data/enemies_gfx/worm_big_head.xml`).
*   **`rect_animation`**: `eat` - The animation to play for the sprite.
*   **`offset_x`, `offset_y`**: Adjusts the sprite's position relative to its origin.
*   **`z_index`**: Controls the layering of sprites, ensuring correct visual order.

## Other Notable Components

*   **`CellEaterComponent`**: Defines the radius (`9`) for consuming cells.
*   **`PathFindingGridMarkerComponent`**: Used for navigation pathfinding.
*   **`GenomeDataComponent`**:
    *   **`herd_id`**: `worm` - Identifies its species for AI interactions.
    *   **`food_chain_rank`**: `6` - Its position in the ecosystem.
    *   **`is_predator`**: `1` - Indicates it hunts other creatures.
*   **`LuaComponent`**:
    *   **`script_death`**: `data/scripts/animals/worm_death.lua` - The script executed upon the worm's death.
*   **`AudioComponent` / `AudioLoopComponent`**: Manages the sound effects and ambient noises associated with the worm.