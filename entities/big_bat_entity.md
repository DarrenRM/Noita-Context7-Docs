---
title: Big Bat Entity
category: entities
---

# Big Bat Entity

This document details the `bigbat.xml` entity, a flying enemy creature in Noita.

## Core Attributes

The Big Bat is a flying enemy with ranged attack capabilities and a light-emitting component.

### Base Entity Configuration

The `Base` tag inherits from `base_enemy_flying.xml`, providing fundamental flying enemy behaviors.

*   **`ItemChestComponent`**: Grants a chance to drop loot upon defeat.
    *   `level`: Set to `2`, indicating a moderate loot tier.

### AI Behavior (`AnimalAIComponent`)

Controls the creature's actions and combat.

*   **Ranged Attack**:
    *   `attack_ranged_enabled`: `1` (enabled).
    *   `attack_ranged_entity_file`: Specifies the projectile used (`data/entities/projectiles/bat.xml`).
    *   `attack_ranged_frames_between`: `250` (cooldown between ranged attacks).
    *   `attack_ranged_offset_y`: `8` (vertical offset for projectile origin).
    *   `attack_ranged_action_frame`: `4` (frame at which the attack animation triggers).
*   **Dash Attack**:
    *   `attack_dash_enabled`: `1` (enabled).
    *   `attack_dash_damage`: `0.5` (damage dealt by the dash).
*   **Movement**:
    *   `needs_food`: `0` (does not require food).
    *   `can_fly`: `1` (inherently capable of flight).

### Damage and Health (`DamageModelComponent`)

Defines the creature's survivability and how it reacts to damage.

*   **Health**: `hp="3.5"`.
*   **Ragdoll**:
    *   `ragdoll_filenames_file`: `data/ragdolls/bigbat/filenames.txt` (defines ragdoll parts).
    *   `ragdoll_material`: `meat_slime` (material of the ragdoll).
    *   `ragdoll_offset_y`: `-5`, `ragdoll_offset_x`: `-1` (positional offset for the ragdoll).
*   **Blood**:
    *   `blood_material`: `slime`.
    *   `blood_spray_material`: `slime`.
    *   `blood_sprite_directional`: `data/particles/bloodsplatters/bloodsplatter_directional_purple_$[1-3].xml`.
    *   `blood_sprite_large`: `data/particles/bloodsplatters/bloodsplatter_purple_$[1-3].xml`.

### Pathfinding (`PathFindingComponent`)

Determines how the entity navigates the environment.

*   `can_fly`: `1` (can navigate through the air).
*   `can_walk`: `0` (cannot walk on ground).

### Visuals (`SpriteComponent`)

Defines the entity's graphical representation.

*   `image_file`: `data/enemies_gfx/bigbat.xml` (path to the sprite definition).
*   `offset_x`, `offset_y`: `0` (no positional offset for the sprite).

### Genetics (`GenomeDataComponent`)

Used for creature grouping and AI interactions.

*   `herd_id`: `bat` (identifies this creature as part of the "bat" herd).

### Hitbox (`HitboxComponent`)

Defines the collision area for interactions.

*   `aabb_min_x`: `-6.0`, `aabb_max_x`: `10.0`.
*   `aabb_min_y`: `-15`, `aabb_max_y`: `5`.
*   `is_enemy`: `1` (identifies as an enemy).

### Character Data (`CharacterDataComponent`)

Provides general character properties.

*   `climb_over_y`: `4` (height it can climb over).
*   `collision_aabb_min_x`: `-6.0`, `collision_aabb_max_x`: `6.0`.
*   `collision_aabb_min_y`: `-13`, `collision_aabb_max_y`: `2`.
*   `mass`: `1.5`.

## Special Components

### Light (`LightComponent`)

The Big Bat emits a colored light.

*   `r`: `80`, `g`: `40`, `b`: `60` (purple-ish hue).
*   `radius`: `64` (range of the light).

### Music Energy (`MusicEnergyAffectorComponent`)

Interacts with the game's music system.

*   `energy_target`: `1` (likely influences music energy levels).

### Audio (`AudioComponent`)

Defines the sound events associated with the Big Bat.

*   **Primary Sound Bank**:
    *   `file`: `data/audio/Desktop/animals.bank`.
    *   `event_root`: `animals/bigbat`.
*   **Wing Flap Sound**:
    *   `file`: `data/audio/Desktop/animals.bank`.
    *   `event_root`: `animals/wing_flap_skin_big`.