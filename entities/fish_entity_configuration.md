---
title: Fish Entity Configuration
category: entities
---

# Fish Entity Configuration

This document details the configuration of the `fish` entity in Noita, focusing on key attributes relevant to AI-assisted modding.

## Entity Definition

The `fish` entity is defined with several tags that categorize its behavior and interactions within the game world.

### Core Tags

*   `mortal`: Indicates the entity can be killed.
*   `hittable`: The entity can be targeted and damaged.
*   `helpless_animal`: Denotes a non-aggressive, vulnerable creature.
*   `prey`: Identifies the entity as a food source for predators.

## Key Components and Attributes

The behavior and properties of the fish are determined by various components. Below are the most significant ones for modding.

### AdvancedFishAIComponent

Controls the AI behavior of the fish.

*   `move_check_range_min`: The minimum range at which the fish checks for movement opportunities.

### GenomeDataComponent

Defines the genetic traits and ecological role of the fish.

*   `herd_id`: Identifies the group or type of herd the fish belongs to (e.g., "helpless").
*   `food_chain_rank`: A numerical value representing its position in the food chain. Higher numbers typically indicate lower positions (prey).
*   `is_predator`: A flag indicating if the entity is a predator (0 for non-predator).

### DamageModelComponent

Manages how the fish takes damage from various sources.

*   `hp`: The entity's health points. A very low value (0.1) suggests it's easily killed.
*   `materials_that_damage`: A list of material types that inflict damage upon contact.
    *   `acid`, `lava`, `poison`, `blood_cold`, `blood_cold_vapour`, `magic_liquid_mana_regeneration`
*   `materials_how_much_damage`: Corresponding damage values for each material in `materials_that_damage`.
    *   `0.004`, `0.004`, `0.001`, `0.0008`, `0.0007`, `0.004`
*   `falling_damage_damage_max`/`min`: Maximum and minimum damage from falling.
*   `falling_damage_height_max`/`min`: The height thresholds for falling damage.
*   `fire_damage_amount`: The amount of damage taken from fire.
*   `fire_probability_of_ignition`: The chance of the fish catching fire.
*   `ragdoll_material`: The material used for the ragdoll effect upon death.

### HitboxComponent

Defines the collision boundaries of the fish.

*   `aabb_min_x`, `aabb_max_x`: Minimum and maximum X-coordinates for the Axis-Aligned Bounding Box.
*   `aabb_min_y`, `aabb_max_y`: Minimum and maximum Y-coordinates for the Axis-Aligned Bounding Box.

### CharacterDataComponent

Contains general character physics and movement properties.

*   `mass`: The mass of the fish.
*   `collision_aabb_min_x`/`max_x`/`min_y`/`max_y`: Defines the collision box used for character interactions.
*   `eff_hg_velocity_min`/`max_x`/`min`/`max_y`: Defines the velocity range for effects like knockback.

### CharacterPlatformingComponent

Governs movement mechanics, including acceleration and velocity limits.

*   `velocity_min_x`/`max_x`: Minimum and maximum horizontal velocity.
*   `velocity_min_y`/`max_y`: Minimum and maximum vertical velocity.
*   `run_velocity`: The base running speed.
*   `accel_x`: Horizontal acceleration.

### SpriteComponent

Handles the visual representation of the fish.

*   `image_file`: Path to the graphical asset file for the fish.
    *   `data/enemies_gfx/fish_01.xml`
*   `rect_animation`: The name of the primary animation to use (e.g., "walk").

### CameraBoundComponent

Manages how the entity interacts with the camera's view.

*   `max_count`: The maximum number of this entity type that can be active within the camera's range.
*   `distance`: The maximum distance from the camera at which the entity can exist.