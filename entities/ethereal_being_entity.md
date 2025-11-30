---
title: Ethereal Being Entity
category: entities
---

# Ethereal Being Entity

This document details the configuration of the Ethereal Being entity in Noita, focusing on its attributes relevant to AI-assisted modding.

## Core Attributes

The Ethereal Being is a hostile, non-teleportable, and non-polymorphable creature with a focus on melee combat and creature detection. It is tagged as a boss helper and is immune to glue.

*   **`name`**: `$animal_ethereal_being`
*   **`tags`**: `enemy,teleportable_NOT,polymorphable_NOT,hittable,mortal,boss_ghost_helper,glue_NOT`

## Combat and AI

The Ethereal Being is designed to be an aggressive, flying enemy that senses creatures even through walls.

### `AnimalAIComponent`

This component governs the creature's behavior and senses.

*   **`preferred_job`**: `JobDefault`
*   **`creature_detection_range_x`**: `300`
*   **`creature_detection_range_y`**: `300`
*   **`attack_dash_enabled`**: `0` (Dash attacks are disabled)
*   **`attack_ranged_enabled`**: `0` (Ranged attacks are disabled)
*   **`attack_melee_enabled`**: `1` (Melee attacks are enabled)
*   **`food_material`**: `blood`
*   **`needs_food`**: `1` (Requires food to survive)
*   **`sense_creatures`**: `1` (Can sense creatures)
*   **`can_fly`**: `1` (Capable of flight)
*   **`aggressiveness_min`**: `1`
*   **`aggressiveness_max`**: `100`
*   **`sense_creatures_through_walls`**: `1` (Can detect creatures through walls)

### `PathFindingComponent`

Defines how the entity navigates the game world.

*   **`can_dive`**: `1`
*   **`can_fly`**: `1`
*   **`can_jump`**: `0`
*   **`can_walk`**: `0`
*   **`cost_of_flying`**: `500`
*   **`frames_between_searches`**: `20`
*   **`frames_to_get_stuck`**: `120`
*   **`max_jump_distance_from_camera`**: `400`

### `DamageModelComponent`

Manages the entity's health and damage resistances/vulnerabilities.

*   **`hp`**: `15.5`
*   **`fire_probability_of_ignition`**: `0`
*   **`ragdoll_material`**: `rock_static_glow`
*   **`blood_material`**: `plasma_fading`
*   **`air_needed`**: `0`
*   **`falling_damages`**: `0`

#### `damage_multipliers`

*   **`projectile`**: `0.0` (Immune to projectile damage)
*   **`fire`**: `0` (Immune to fire damage)
*   **`ice`**: `0` (Immune to ice damage)
*   **`holy`**: `1.2` (Takes increased damage from holy sources)

### `HitboxComponent`

Defines the physical collision area of the entity.

*   **`aabb_min_x`**: `-16`
*   **`aabb_max_x`**: `16`
*   **`aabb_min_y`**: `-16`
*   **`aabb_max_y`**: `16`
*   **`is_enemy`**: `1`

### `DamageNearbyEntitiesComponent`

This component allows the entity to damage other entities within a radius. There are two instances, likely for different damage application timings or effects.

*   **`radius`**: `16`
*   **`time_between_damaging`**: `40` (for the first instance) and `3` (for the second)
*   **`damage_min`**: `0.16`
*   **`damage_max`**: `0.32`
*   **`target_tag`**: `player_unit`
*   **`damage_description`**: `$ethereal_damage`
*   **`damage_type`**: `DAMAGE_CURSE`

## Visuals and Physics

### `SpriteComponent`

Handles the visual representation of the Ethereal Being.

*   **`image_file`**: `data/enemies_gfx/ethereal_being.xml`
*   **`emissive`**: `1` (Emits light)
*   **`additive`**: `1` (Uses additive blending for rendering)
*   **`z_index`**: `0.9`
*   **`has_special_scale`**: `1`

### `PhysicsAIComponent`

Controls the entity's physics-based movement and reactions.

*   **`target_vec_max_len`**: `15.0`
*   **`force_coeff`**: `14.0`
*   **`force_max`**: `160`
*   **`torque_coeff`**: `50`
*   **`torque_max`**: `50.0`
*   **`damage_deactivation_probability`**: `0`
*   **`free_if_static`**: `1`

### `PhysicsBodyComponent`

Defines the physical properties of the entity's body.

*   **`angular_damping`**: `0.02`
*   **`fixed_rotation`**: `1`
*   **`is_bullet`**: `0`
*   **`linear_damping`**: `0`

### `ParticleEmitterComponent`

Generates visual effects, in this case, blue sparks.

*   **`emitted_material_name`**: `spark_blue_dark`
*   **`gravity.y`**: `0`
*   **`count_min`**: `3`
*   **`count_max`**: `6`
*   **`lifetime_min`**: `0.8`
*   **`lifetime_max`**: `2.0`
*   **`emit_cosmetic_particles`**: `1`
*   **`emission_interval_min_frames`**: `1`
*   **`emission_interval_max_frames`**: `2`
*   **`is_emitting`**: `1`

## Scripting and Audio

### `LuaComponent`

Integrates custom Lua scripts for advanced behavior.

*   **`script_source_file`**: `data/scripts/animals/ethereal_check.lua` (Executed every 5 frames)
*   **`script_death`**: `data/scripts/animals/log_kill.lua` (Executed on death)

### `AudioLoopComponent`

Manages ambient sound effects.

*   **`file`**: `data/audio/Desktop/animals.bank`
*   **`event_name`**: `animals/ghost/movement_loop`
*   **`auto_play`**: `1`

## Other Components

*   **`ItemChestComponent`**: `level="4" enemy_drop="1"` - Indicates loot drop capabilities.
*   **`PathFindingGridMarkerComponent`**: Used for pathfinding grid calculations.
*   **`GenomeDataComponent`**: `herd_id="ghost"`, `food_chain_rank="10"`, `is_predator="1"` - Defines its place in the ecosystem.
*   **`CharacterPlatformingComponent`**: `accel_x="1"`, `pixel_gravity="100"`, `jump_velocity_y="-8"`, `run_velocity="12"` - Basic movement parameters.
*   **`SpriteAnimatorComponent`**: Enables sprite animations.
*   **`CameraBoundComponent`**: `max_count="20"`, `distance="160000"` - Controls entity visibility based on camera distance.
*   **`GameStatsComponent`**: Tracks game statistics related to this entity.
*   **`GameEffectComponent`**: `effect="PROTECTION_PROJECTILE"`, `frames="-1"` - Grants projectile protection indefinitely.