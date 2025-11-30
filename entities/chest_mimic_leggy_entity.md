---
title: Chest Mimic (Leggy) Entity
category: entities
---

---

# Chest Mimic (Leggy) Entity

This document details the configuration for the "Chest Mimic (Leggy)" entity in Noita, focusing on its AI, physics, damage, and visual components.

## Core Attributes

*   **`name`**: `$animal_lukki` (Internal identifier, likely a placeholder or shared name with other Lukki variants)
*   **`tags`**: `enemy`, `mortal`, `hittable`, `homing_target`, `teleportable_NOT`, `glue_NOT` (Defines its behavior and interactions within the game world)

## AI Components

### AnimalAIComponent

This component governs the creature's behavior and senses.

*   **`preferred_job`**: `JobDefault` (Indicates its default AI routine)
*   **`creature_detection_range_x`**: `700` (Horizontal range for detecting other creatures)
*   **`creature_detection_range_y`**: `10` (Vertical range for detecting other creatures)
*   **`food_material`**: `meat` (Specifies what it considers food)
*   **`needs_food`**: `0` (Indicates it does not require food to survive)
*   **`sense_creatures`**: `1` (Enables creature sensing)
*   **`attack_ranged_enabled`**: `0` (Cannot attack from range)
*   **`attack_melee_enabled`**: `1` (Can attack in melee)
*   **`aggressiveness_min`**: `95`
*   **`aggressiveness_max`**: `100` (Highly aggressive)
*   **`is_static_turret`**: `1` (Behaves like a stationary turret)
*   **`attack_melee_max_distance`**: `15` (Maximum distance for melee attacks)
*   **`attack_melee_damage_min`**: `0.6`
*   **`attack_melee_damage_max`**: `1.0` (Melee damage range)

### PathFindingComponent

Defines how the entity navigates the game world.

*   **`can_dive`**: `1`
*   **`can_fly`**: `1`
*   **`can_swim_on_surface`**: `1`
*   **`can_walk`**: `1`
*   **`cost_of_flying`**: `500` (High cost, suggesting it prefers not to fly)
*   **`initial_jump_max_distance_x`**: `100`
*   **`initial_jump_max_distance_y`**: `60`
*   **`jump_speed`**: `200`

### PhysicsAIComponent

Controls the entity's physical interactions and movement.

*   **`target_vec_max_len`**: `15.0`
*   **`force_coeff`**: `10.0`
*   **`torque_coeff`**: `50`

## Visual Components

### SpriteComponent

Determines the entity's visual appearance.

*   **`image_file`**: `data/enemies_gfx/chest_mimic.xml` (References the sprite definition for a chest mimic)

### LightComponent

Adds a light source to the entity.

*   **`radius`**: `64`
*   **`fade_out_time`**: `0.75`
*   **`r`, `g`, `b`**: `255` (White light)

## Damage and Health

### DamageModelComponent

Manages the entity's health and how it takes damage.

*   **`hp`**: `6` (Hit points)
*   **`fire_damage_amount`**: `2.2`
*   **`fire_probability_of_ignition`**: `0.5`
*   **`materials_damage`**: `acid` (Can be damaged by acid)
*   **`materials_how_much_damage`**: `0.1`

#### `damage_multipliers`

*   **`melee`**: `2.0` (Takes double damage from melee)
*   **`projectile`**: `1.0`
*   **`explosion`**: `0.5` (Takes half damage from explosions)
*   **`electricity`**: `1.2`
*   **`fire`**: `1.2`
*   **`holy`**: `2.0` (Takes double damage from holy sources)

### HitboxComponent

Defines the entity's collision area, including a weak spot.

*   **`_tags`**: `hitbox_weak_spot`
*   **`aabb_min_x`, `aabb_max_x`**: `-10`, `10`
*   **`aabb_min_y`, `aabb_max_y`**: `-10`, `10`
*   **`damage_multiplier`**: `1.0` (Standard damage multiplier for this hitbox)

## Other Components

### GenomeDataComponent

Provides information for AI and world generation.

*   **`food_chain_rank`**: `5`
*   **`herd_id`**: `ghost`
*   **`is_predator`**: `1`

### AudioComponent

Manages the entity's sound effects.

*   **`file`**: `data/audio/Desktop/animals.bank`
*   **`event_root`**: `animals`

### SpriteAnimatorComponent

Handles sprite animations.

*   **`rotate_to_surface_normal`**: `0`

### LuaComponent

Allows for custom scripting.

*   **`script_death`**: `data/scripts/animals/chest_leggy_death.lua` (Script executed upon death)

## Limbs

The entity is composed of several limb entities, defining its physical structure and movement.

*   **Left Limbs**: `data/entities/animals/lukki/lukki_feet/chest_limb_left.xml` (Multiple instances with varying `position.x`)
*   **Right Limbs**: `data/entities/animals/lukki/lukki_feet/chest_limb_right.xml` (Multiple instances with varying `position.x`)
*   **Attacker Limb**: `data/entities/animals/lukki/lukki_feet/chest_limb_attacker.xml` (A dedicated limb for attacking)