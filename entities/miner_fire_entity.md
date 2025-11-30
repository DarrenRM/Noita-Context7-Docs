---
title: Miner Fire Entity
category: entities
---

# Miner Fire Entity

This document details the configuration for the "Miner Fire" entity in Noita, primarily focusing on its AI, combat, and physical attributes for modding purposes.

## Core Attributes

The Miner Fire is a basic enemy with a focus on ranged attacks and some unique properties.

### `Base` Entity Configuration

The entity inherits fundamental behaviors from `base_enemy_basic.xml`.

### `AnimalAIComponent`

This component governs the creature's behavior and combat logic.

*   **`preferred_job`**: `JobDefault` - Indicates its default AI state.
*   **`escape_if_damaged_probability`**: `40` - Has a 40% chance to flee when damaged.
*   **`attack_melee_damage_min`**: `0.4` - Minimum melee damage.
*   **`attack_melee_damage_max`**: `0.7` - Maximum melee damage.
*   **`creature_detection_range_x`**: `300` - Horizontal range for detecting creatures.
*   **`creature_detection_range_y`**: `300` - Vertical range for detecting creatures.
*   **`food_material`**: `meat` - What it considers food.
*   **`needs_food`**: `0` - Does not require food to survive.
*   **`sense_creatures`**: `1` - Actively senses other creatures.
*   **`attack_ranged_enabled`**: `1` - Ranged attacks are enabled.
*   **`attack_melee_enabled`**: `0` - Melee attacks are disabled.
*   **`attack_ranged_action_frame`**: `4` - The frame at which the ranged attack is initiated.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/cocktail.xml` - The projectile used for ranged attacks.
*   **`attack_ranged_frames_between`**: `120` - Cooldown in frames between ranged attacks.

### `DamageModelComponent`

Defines the entity's health and how it takes damage.

*   **`hp`**: `2.0` - Hit points of the entity.
*   **`materials_create_messages`**: `1` - Creates messages when materials are affected.
*   **`ragdoll_filenames_file`**: `data/ragdolls/miner_fire/filenames.txt` - Specifies ragdoll files for death animations.
*   **`fire_probability_of_ignition`**: `0` - Cannot be ignited by fire.
*   **`blood_material`**: `blood` - The material of its blood.
*   **`blood_spray_material`**: `blood` - The material of its blood spray.
*   **`blood_spray_create_some_cosmetic`**: `1` - Creates cosmetic blood effects.

#### `damage_multipliers`

*   **`explosion`**: `0.4` - Takes 40% damage from explosions.
*   **`fire`**: `0.2` - Takes 20% damage from fire.

### `SpriteComponent`

Determines the visual appearance of the entity.

*   **`image_file`**: `data/enemies_gfx/miner_fire.xml` - The sprite sheet for the Miner Fire.
*   **`offset_x`**: `0`
*   **`offset_y`**: `0`

### `PathFindingComponent`

Defines how the entity navigates the game world.

*   **`can_jump`**: `1` - Can jump.
*   **`can_fly`**: `0` - Cannot fly.
*   **`jump_speed`**: `120`
*   **`initial_jump_lob`**: `1`
*   **`initial_jump_max_distance_x`**: `60`
*   **`initial_jump_max_distance_y`**: `60`
*   **`can_swim_on_surface`**: `1` - Can swim on the surface of liquids.
*   **`can_dive`**: `1` - Can dive into liquids.

### `CharacterPlatformingComponent`

Controls movement speed and jumping mechanics.

*   **`jump_velocity_y`**: `-15` - The vertical velocity applied when jumping.
*   **`run_velocity`**: `15` - The horizontal movement speed.

### `HitboxComponent`

Defines the collision boundaries for the entity.

*   **`aabb_min_x`**: `-3`
*   **`aabb_max_x`**: `3`
*   **`aabb_min_y`**: `-6`
*   **`aabb_max_y`**: `3`

### `CharacterDataComponent`

Further defines physical properties like mass and collision.

*   **`collision_aabb_min_x`**: `-2.0`
*   **`collision_aabb_max_x`**: `2.0`
*   **`collision_aabb_min_y`**: `-7.5`
*   **`collision_aabb_max_y`**: `3`
*   **`mass`**: `1.3`

## Additional Components

### `LightComponent`

Adds a light source to the entity.

*   **`radius`**: `50` - The radius of the light.
*   **`fade_out_time`**: `1.5` - How long it takes for the light to fade out.

### `AudioComponent`

Manages the entity's sound effects.

*   **`file`**: `data/audio/Desktop/animals.bank` - The audio bank file.
*   **`event_root`**: `animals/miner_fire` - The root event for its sounds.

### `GameEffectComponent`

Applies a persistent game effect.

*   **`effect`**: `ALLERGY_RADIOACTIVE` - The entity emits a radioactive aura.
*   **`frames`**: `-1` - The effect is permanent.

### `LuaComponent`

Allows for custom scripting.

*   **`script_source_file`**: `data/scripts/animals/limit_projectiles.lua` - A script to limit projectile usage.
*   **`execute_every_n_frame`**: `80` - The script runs every 80 frames.