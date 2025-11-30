---
title: Sniper Hell Entity
category: entities
---

# Sniper Hell Entity

This document details the configuration of the "Sniper Hell" entity in Noita, focusing on its attributes relevant to AI-assisted modding.

## Core Attributes

The Sniper Hell is a hostile creature with ranged attack capabilities and moderate health.

### `Base` Entity Configuration

The entity inherits fundamental properties from `base_enemy_basic.xml`.

### `AnimalAIComponent`

This component governs the creature's behavior, including combat, detection, and movement.

*   **`preferred_job`**: `JobDefault` - Indicates its default role.
*   **`escape_if_damaged_probability`**: `70` - High chance to flee when damaged.
*   **`attack_melee_damage_min` / `max`**: `1.4` / `1.7` - Melee damage range.
*   **`creature_detection_range_x` / `y`**: `700` - How far it can detect other creatures.
*   **`attack_melee_max_distance`**: `10` - Maximum range for melee attacks.
*   **`sense_creatures`**: `1` - Actively senses other creatures.
*   **`attack_ranged_enabled`**: `1` - Ranged attacks are active.
*   **`attack_ranged_min_distance` / `max_distance`**: `10` / `800` - Range for ranged attacks.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/sniperbullet_hell.xml` - The projectile it fires.
*   **`attack_ranged_entity_count_min` / `max`**: `4` / `8` - Number of projectiles fired per volley.
*   **`attack_ranged_frames_between`**: `100` - Delay between ranged attacks.
*   **`attack_ranged_use_laser_sight`**: `1` - Utilizes a laser sight for aiming.
*   **`aggressiveness_min` / `max`**: `80` / `100` - Highly aggressive.

### `DamageModelComponent`

Defines the entity's health and how it takes damage.

*   **`hp`**: `4.8` - Hit points.
*   **`blood_spray_material` / `blood_material`**: `liquid_fire` - Spawns fire liquid when damaged.
*   **`damage_multipliers`**:
    *   `projectile`: `0.6` - Reduced damage from projectiles.
    *   `explosion`: `0.6` - Reduced damage from explosions.
    *   `holy`: `2.0` - Takes double damage from holy sources.

### `SpriteComponent`

Handles the visual representation of the entity.

*   **`image_file`**: `data/enemies_gfx/sniper_hell.xml` - Main sprite.
*   **`overlay_image_file`**: `data/enemies_gfx/sniper_hell_overlay.xml` - Overlay sprite, likely for animations or effects.

### `PathFindingComponent`

Determines the entity's movement capabilities, including jumping.

*   **`can_jump`**: `1` - Capable of jumping.
*   **`jump_speed`**: `70`
*   **`initial_jump_max_distance_x` / `y`**: `60` / `50` - Maximum jump distances.
*   **`jump_trajectories`**: Defines specific jump arcs for movement.

### `CharacterPlatformingComponent`

Controls basic character movement parameters.

*   **`jump_velocity_y`**: `-16` - Vertical jump force.
*   **`run_velocity`**: `32` - Horizontal movement speed.

## Other Notable Components

### `LightComponent`

*   **`radius`**: `30` - Light radius.
*   **`r`, `g`**: `190`, `200` - Light color (warm white/yellowish).

### `SpriteComponent` (Laser Sight)

*   **`_tags`**: `laser_sight` - Identifies this sprite for targeting.
*   **`image_file`**: `data/particles/laser_red.png` - Visual for the laser sight.
*   **`visible`**: `0` - Initially hidden, likely toggled by AI.

### `AudioComponent`

*   **`file`**: `data/audio/Desktop/animals.bank` - Sound bank.
*   **`event_root`**: `animals/sniper` - Base sound event name.

### `ParticleEmitterComponent`

*   **`emitted_material_name`**: `blood` - Spawns blood particles.
*   Configured for cosmetic blood spray on hit.

### `GameEffectComponent`

*   **`effect`**: `ALLERGY_RADIOACTIVE` - Applies a radioactive effect.
*   **`frames`**: `-1` - Effect is permanent.