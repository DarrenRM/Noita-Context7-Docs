---
title: Thundermage Entity
category: entities
---

# Thundermage Entity

This document details the Thundermage entity, a flying, electrically charged enemy in Noita.

## Core Attributes

The Thundermage is a basic enemy with several key characteristics:

*   **Name:** `$animal_thundermage`
*   **Tags:** `thundermage`
*   **Base Entity:** `data/entities/base_enemy_basic.xml`

## Key Components and Their Functions

### AnimalAIComponent

This component governs the Thundermage's behavior and combat capabilities.

*   **`preferred_job`**: `JobDefault` - Standard AI behavior.
*   **`attack_melee_damage_min` / `attack_melee_damage_max`**: `0.4` / `0.7` - Defines the minimum and maximum damage for melee attacks.
*   **`creature_detection_range_x` / `creature_detection_range_y`**: `300` - The range at which the Thundermage detects other creatures.
*   **`food_material`**: `blood` - Indicates its dietary preference.
*   **`needs_food`**: `0` - The Thundermage does not require food.
*   **`sense_creatures`**: `1` - It is capable of sensing creatures.
*   **`attack_ranged_enabled`**: `1` - Ranged attacks are enabled.
*   **`can_fly`**: `1` - The Thundermage can fly.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/thunderball.xml` - Specifies the projectile used for ranged attacks.
*   **`attack_ranged_action_frame`**: `6` - The frame at which the ranged attack is initiated.
*   **`attack_ranged_frames_between`**: `140` - The number of frames between ranged attacks.

### DamageModelComponent

Defines the Thundermage's health and resistances.

*   **`hp`**: `5` - The Thundermage has 5 hit points.
*   **`ragdoll_material`**: `diamond` - The material used for its ragdoll.
*   **`fire_probability_of_ignition`**: `0` - It cannot be ignited by fire.
*   **`electricity`**: `-1` - Immune to electricity damage.
*   **`explosion` / `holy`**: `0.5` - Takes half damage from explosions and holy attacks.

### SpriteComponent

Controls the visual appearance of the Thundermage.

*   **`image_file`**: `data/enemies_gfx/thundermage.xml` - The primary sprite file.
*   **`offset_x` / `offset_y`**: `0` - No offset for the main sprite.

### CharacterPlatformingComponent

Manages movement and physics.

*   **`jump_velocity_y`**: `-12` - The vertical velocity applied when jumping.
*   **`run_velocity`**: `18` - The movement speed when running.

### HitboxComponent

Defines the collision boundaries of the entity.

*   **`aabb_min_x` / `aabb_max_x`**: `-4.5` / `4.5` - X-axis bounds for the hitbox.
*   **`aabb_min_y` / `aabb_max_y`**: `-14` / `3` - Y-axis bounds for the hitbox.

### ElectricChargeComponent

Enables electrical properties.

*   **`charge_time_frames`**: `2` - The duration of electrical charge.
*   **`electricity_emission_interval_frames`**: `10` - The interval between electrical discharges.

### LightComponent

Adds a light source to the entity.

*   **`r` / `g` / `b`**: `120` / `180` / `220` - Defines the light color (a bluish-white).
*   **`radius`**: `64` - The radius of the light emitted.

### SpriteComponent (Emissive)

Handles the emissive sprite for visual effects.

*   **`image_file`**: `data/enemies_gfx/thundermage_emissive.xml` - The file for the emissive sprite.
*   **`emissive`**: `1` - Enables emissive rendering.
*   **`additive`**: `1` - Uses additive blending for the emissive effect.
*   **`rect_animation`**: `walk` - Specifies the animation to use.

### AudioLoopComponent

Manages ambient sound effects.

*   **`file`**: `data/audio/Desktop/animals.bank` - The audio bank containing the sound.
*   **`event_name`**: `animals/thundermage/movement_loop` - The specific sound event for movement.
*   **`auto_play`**: `1` - The sound plays automatically.