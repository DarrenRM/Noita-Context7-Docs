---
title: Bloom Entity
category: entities
---

# Bloom Entity

This document details the `bloom.xml` entity, a basic enemy type in Noita.

## Core Attributes

The Bloom is a small, mobile enemy with ranged attack capabilities.

### Base Entity Configuration

The entity inherits from `base_enemy_basic.xml`, providing fundamental enemy behaviors.

### Animal AI Component

This component governs the Bloom's artificial intelligence and combat behavior.

*   **`preferred_job`**: `JobDefault` - Indicates its standard AI behavior.
*   **`escape_if_damaged_probability`**: `50` - Has a 50% chance to flee when damaged.
*   **`attack_ranged_min_distance`**: `0` - Can attack at very close range.
*   **`attack_ranged_max_distance`**: `250` - Has a maximum ranged attack distance.
*   **`creature_detection_range_x` / `creature_detection_range_y`**: `300` - Detects creatures within a 300-unit radius.
*   **`food_material`**: `blood` - Its preferred food source.
*   **`needs_food`**: `0` - Does not require food to survive.
*   **`sense_creatures`**: `1` - Actively senses other creatures.
*   **`attack_ranged_enabled`**: `1` - Ranged attacks are enabled.
*   **`attack_melee_enabled`**: `0` - Melee attacks are disabled.
*   **`attack_ranged_action_frame`**: `4` - The frame on which the ranged attack is initiated.
*   **`attack_ranged_frames_between`**: `60` - Cooldown between ranged attacks.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/dummy.xml` - The projectile used for ranged attacks.

### Damage Model Component

Defines the Bloom's health and how it reacts to damage.

*   **`hp`**: `4` - Has 4 hit points.
*   **`ragdoll_material`**: `meat_slime_green` - The material used for its ragdoll upon death.
*   **`blood_material`**: `slime` - The type of blood it produces.
*   **`blood_sprite_directional`**: `data/particles/bloodsplatters/bloodsplatter_directional_purple_$[1-3].xml` - The particle effect for directional blood splatters.
*   **`blood_sprite_large`**: `data/particles/bloodsplatters/bloodsplatter_purple_$[1-3].xml` - The particle effect for large blood splatters.

### Sprite Component

Determines the visual appearance of the Bloom.

*   **`image_file`**: `data/enemies_gfx/bloom.xml` - Specifies the graphical asset for the Bloom.

### Path Finding Component

Controls the Bloom's movement and navigation capabilities.

*   **`can_jump`**: `1` - Capable of jumping.
*   **`jump_speed`**: `140` - The speed at which it jumps.
*   **`initial_jump_max_distance_x`**: `80` - Maximum horizontal jump distance.
*   **`initial_jump_max_distance_y`**: `60` - Maximum vertical jump distance.

### Genome Data Component

Provides genetic information relevant to its role in the ecosystem.

*   **`herd_id`**: `flower` - Identifies its herd or species group.
*   **`food_chain_rank`**: `7` - Its position in the food chain.
*   **`is_predator`**: `1` - It is a predator.

### Character Platforming Component

Defines its basic movement characteristics.

*   **`run_velocity`**: `12` - Its running speed.

### Hitbox Component

Defines the collision area for the Bloom.

*   **`aabb_max_x`**: `8`
*   **`aabb_max_y`**: `4`
*   **`aabb_min_x`**: `-8`
*   **`aabb_min_y`**: `-12`

### Lua Component

Attaches custom Lua scripting for additional behaviors.

*   **`script_shot`**: `data/scripts/projectiles/bloom_shot.lua` - The script controlling its projectile behavior.
*   **`limit_to_every_n_frame`**: `59` - Limits the script execution to once every 59 frames.

### Audio Components

Handle the sound effects associated with the Bloom.

*   **`AudioLoopComponent`**: Plays a looping movement sound.
*   **`AudioComponent`**: Defines the root sound event for the Bloom.