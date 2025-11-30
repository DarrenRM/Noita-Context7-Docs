---
title: Meat Maggot Entity
category: entities
---

# Meat Maggot Entity

This document details the configuration of the Meat Maggot entity in Noita, focusing on its core attributes and behaviors for AI-assisted modding.

## Core Attributes

The Meat Maggot is a hostile, worm-like creature with a focus on close-quarters combat and consumption.

*   **`name`**: `$animal_meatmaggot` - The internal identifier for the Meat Maggot.
*   **`tags`**: `mortal, hittable, teleportable_NOT, homing_target, enemy, worm, glue_NOT` - Defines its fundamental properties, including being a living, targetable enemy that cannot be teleported or glued.

## Components

### WormComponent

Manages the physical and movement properties of the worm-like body.

*   **`acceleration`**: `0.3` - How quickly the maggot reaches its top speed.
*   **`gravity`**: `4` - The gravitational pull affecting the main body.
*   **`tail_gravity`**: `30` - The stronger gravitational pull on the tail segments, keeping them grounded.
*   **`part_distance`**: `6` - The spacing between individual body segments.
*   **`hitbox_radius`**: `2` - The size of the collision area for the maggot.
*   **`bite_damage`**: `0.4` - The amount of damage dealt by a bite attack.
*   **`ragdoll_filename`**: `data/ragdolls/meatmaggot/filenames.txt` - Specifies the ragdoll configuration file.

### WormAIComponent

Controls the artificial intelligence and target acquisition behavior.

*   **`speed`**: `3` - The base movement speed.
*   **`speed_hunt`**: `4` - The increased speed when actively hunting a target.
*   **`hunt_box_radius`**: `256` - The radius within which the maggot will actively seek out targets.
*   **`random_target_box_radius`**: `128` - The radius for seeking random points to move towards when no target is present.
*   **`give_up_time_frames`**: `290` - The number of frames before the maggot gives up on its current target.

### CellEaterComponent

Enables the maggot to consume certain materials.

*   **`radius`**: `3` - The radius around the maggot where it can consume materials.
*   **`only_stain`**: `1` - Indicates it primarily consumes stains rather than solid materials.

### DamageModelComponent

Defines the health, resistances, and damage vulnerabilities.

*   **`hp`**: `3.5` - The total health points of the Meat Maggot.
*   **`fire_damage_amount`**: `0.2` - The damage taken from fire per tick.
*   **`fire_probability_of_ignition`**: `0.5` - The chance of igniting when hit by fire.
*   **`blood_material`**: `blood_worm` - The material used for blood splatters.
*   **`materials_that_damage`**: `acid` - Specifies materials that inflict damage on contact.
*   **`materials_how_much_damage`**: `0.1` - The amount of damage taken from specified materials.

#### Damage Multipliers

*   **`drill`**: `0.4` - Reduced damage taken from drills.
*   **`slice`**: `1.2` - Increased damage taken from slicing attacks.
*   **`projectile`**: `0.5` - Reduced damage taken from projectiles.

### GenomeDataComponent

Relates to the creature's place in the ecosystem and its genetic properties.

*   **`herd_id`**: `worm` - Identifies it as part of the "worm" herd.
*   **`food_chain_rank`**: `18` - Its position in the food chain.
*   **`is_predator`**: `1` - Indicates it is a predator.

### Sprite Components

These define the visual appearance of the Meat Maggot, broken down into head, body segments, and tail. Each `SpriteComponent` typically includes:

*   **`image_file`**: Path to the sprite's graphical asset.
*   **`rect_animation`**: The current animation state (e.g., "eat", "stand").
*   **`next_rect_animation`**: The animation to transition to.
*   **`offset_x`, `offset_y`**: Positioning adjustments for the sprite.
*   **`z_index`**: Controls the layering of sprites.

The Meat Maggot has a distinct head sprite and multiple body/tail sprites to create its segmented appearance.

### Audio Components

*   **`AudioComponent`**: Defines the sound bank and event roots for general and worm-specific sounds.
*   **`AudioLoopComponent`**: Manages looping movement sounds with adjustable speed parameters.

---