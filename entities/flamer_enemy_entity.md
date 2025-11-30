---
title: Flamer Enemy Entity
category: entities
---

# Flamer Enemy Entity

This document details the configuration of the Flamer enemy entity in Noita, focusing on attributes relevant for AI-assisted modding.

## Core Attributes

The Flamer is a flying robot enemy with a ranged flamethrower attack.

### `Base` Component

This entity inherits from `base_enemy_robot.xml`, providing fundamental robot enemy characteristics.

### `AnimalAIComponent`

This component governs the Flamer's behavior and combat capabilities.

*   **`preferred_job`**: `JobDefault` - Indicates its standard operational role.
*   **`escape_if_damaged_probability`**: `4` - A low chance to flee when damaged.
*   **`attack_melee_damage_min` / `attack_melee_damage_max`**: `0.4` / `0.7` - Defines its melee damage range (though melee is disabled).
*   **`creature_detection_range_x` / `creature_detection_range_y`**: `400` - The horizontal and vertical range for detecting creatures.
*   **`creature_detection_angular_range_deg`**: `60` - The angular field of view for creature detection.
*   **`attack_melee_enabled`**: `0` - Melee attacks are disabled for this entity.
*   **`attack_ranged_enabled`**: `1` - Ranged attacks are enabled.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/flamethrower.xml` - Specifies the projectile used for its ranged attack.
*   **`attack_ranged_frames_between`**: `2` - The number of frames between ranged attacks.
*   **`attack_ranged_max_distance`**: `70` - The maximum distance for its ranged attack.
*   **`can_fly`**: `1` - The Flamer is capable of flight.
*   **`aggressiveness_min` / `aggressiveness_max`**: `1` / `60` - Defines its aggression level.

### `DamageModelComponent`

Manages the Flamer's health and damage-related properties.

*   **`hp`**: `2` - The Flamer's hit points.
*   **`ragdoll_material`**: `steel` - The material used for its ragdoll when destroyed.
*   **`blood_material`**: `oil` - The material that spills when damaged.

### `SpriteComponent`

Defines the visual representation of the Flamer.

*   **`image_file`**: `data/enemies_gfx/flamer.xml` - Points to the sprite definition file.

### `PathFindingComponent`

Handles the Flamer's movement and navigation.

*   **`can_fly`**: `1` - Explicitly states its ability to fly.
*   **`initial_jump_max_distance_x` / `initial_jump_max_distance_y`**: `60` - Maximum horizontal and vertical jump distances.

### `CharacterPlatformingComponent`

Controls movement parameters for characters.

*   **`fly_velocity_x`**: `28` - The horizontal speed when flying.
*   **`run_velocity`**: `20` - The ground movement speed.

## Visual and Functional Elements

### `ParticleEmitterComponent`

This component is responsible for the visual effects associated with the Flamer's propulsion.

*   **`_tags`**: `jetpack` - Identifies this as a jetpack effect.
*   **`emitted_material_name`**: `rocket_particles` - The material used for the emitted particles.
*   **`y_vel_min` / `y_vel_max`**: `80` / `180` - The vertical velocity range of the emitted particles.
*   **`lifetime_min` / `lifetime_max`**: `0.1` / `0.2` - The duration of each particle.
*   **`emit_cosmetic_particles`**: `1` - Ensures these are cosmetic effects.
*   **`is_emitting`**: `1` - The particle emitter is active.

### `LightComponent`

Adds a light source to the entity.

*   **`radius`**: `50` - The radius of the light emitted.
*   **`fade_out_time`**: `1.5` - The time it takes for the light to fade out.

### `ItemPickUpperComponent`

Indicates that this entity can be picked up by other entities.

*   **`is_in_npc`**: `1` - Suggests it's intended to be picked up by NPCs.