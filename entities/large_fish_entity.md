---
title: Large Fish Entity
category: entities
---

---

# Large Fish Entity

This document details the configuration for the large fish entity in Noita, focusing on key attributes relevant to AI-assisted modding.

## Core Entity Attributes

*   **`name`**: `$animal_fish_large` - The internal identifier for this entity.
*   **`tags`**: `mortal,hittable,helpless_animal,prey` - Defines its fundamental properties: it can die, be hit, is a non-aggressive animal, and serves as prey.

## Key Components and Their Attributes

### AdvancedFishAIComponent

Controls the fish's movement and AI behavior.

*   **`move_check_range_min`**: `8` - The minimum range at which the AI checks for movement opportunities.

### GenomeDataComponent

Defines the fish's place in the ecosystem.

*   **`herd_id`**: `helpless` - Identifies it as part of a "helpless" group.
*   **`food_chain_rank`**: `1000` - A high rank, indicating it's low on the food chain.
*   **`is_predator`**: `0` - Explicitly marks it as not a predator.

### DamageModelComponent

Manages health and damage-related properties.

*   **`hp`**: `0.1` - Very low health, making it easily defeatable.
*   **`falling_damage_damage_max`**: `1.2` - Maximum damage taken from falls.
*   **`falling_damage_height_max`**: `450` - The height at which maximum falling damage is applied.
*   **`fire_damage_amount`**: `0.2` - The amount of damage taken from fire.
*   **`fire_probability_of_ignition`**: `0.5` - 50% chance to ignite when exposed to fire.

### HitboxComponent

Defines the physical collision boundaries of the fish.

*   **`aabb_max_x`**: `3.5`
*   **`aabb_max_y`**: `4`
*   **`aabb_min_x`**: `-3.5`
*   **`aabb_min_y`**: `-3`

### CharacterDataComponent

General character properties, including mass and collision box.

*   **`mass`**: `0.3` - The physical mass of the fish.
*   **`collision_aabb_min_x`**: `-3`
*   **`collision_aabb_max_x`**: `3`
*   **`collision_aabb_min_y`**: `-3`
*   **`collision_aabb_max_y`**: `3`

### CharacterPlatformingComponent

Governs movement physics and speed.

*   **`run_velocity`**: `60` - The base speed of the fish.
*   **`accel_x`**: `0.15` - The acceleration rate on the X-axis.
*   **`velocity_max_y`**: `200` - Maximum upward velocity.

### SpriteComponent

Handles the visual representation of the fish.

*   **`image_file`**: `data/enemies_gfx/fish_02.xml` - Points to the graphical asset used for the fish.
*   **`rect_animation`**: `walk` - Specifies the default animation state.

### CameraBoundComponent

Manages how the entity interacts with the camera's view.

*   **`max_count`**: `64` - The maximum number of these entities that can be active within the camera's bounds.
*   **`distance`**: `2000` - The radius around the camera within which these entities are considered.