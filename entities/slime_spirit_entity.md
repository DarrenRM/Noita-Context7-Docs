---
title: Slime Spirit Entity
category: entities
---

# Slime Spirit Entity

This document details the configuration of the Slime Spirit entity in Noita, focusing on its AI, combat, and visual properties.

## Core Attributes

The Slime Spirit is a flying, non-aggressive creature with a unique particle emission effect.

*   **Name:** `$animal_slimespirit`
*   **Tags:** `glue_NOT` (Indicates it does not interact with glue in a specific way)
*   **Base Entity:** `data/entities/base_enemy_flying.xml` (Inherits general flying enemy properties)

## AI Behavior (`AnimalAIComponent`)

The Slime Spirit exhibits passive AI, prioritizing evasion over direct combat.

*   **`preferred_job`**: `JobDefault` (Standard AI behavior)
*   **`escape_if_damaged_probability`**: `35` (35% chance to flee when damaged)
*   **`creature_detection_range_x` / `creature_detection_range_y`**: `250` (Detects creatures within a 250-unit radius)
*   **`sense_creatures`**: `1` (Actively senses nearby creatures)
*   **`can_fly`**: `1` (Capable of flight)
*   **`needs_food`**: `0` (Does not require food)
*   **`food_material`**: `meat` (Designated food material, though not actively used for sustenance)
*   **Combat Disabled:** `attack_ranged_enabled="0"`, `attack_melee_enabled="0"`, `attack_dash_enabled="0"` (Cannot initiate ranged, melee, or dash attacks)

## Damage and Health (`DamageModelComponent`)

The Slime Spirit has low health and specific damage resistances/vulnerabilities.

*   **`hp`**: `3` (Low health pool)
*   **`fire_probability_of_ignition`**: `0` (Cannot be ignited by fire)
*   **`ragdoll_material`**: `rock_static_glow` (Defines the material for its ragdoll effect)
*   **`blood_material`**: `plasma_fading` (Specifies the material for blood effects)
*   **`air_needed`**: `0` (Does not require air to survive)

### Damage Multipliers

*   **`projectile`**: `0.8` (Takes 80% damage from projectiles)
*   **`explosion`**: `0.8` (Takes 80% damage from explosions)
*   **`electricity`**: `1` (Takes normal damage from electricity)
*   **`fire`**: `0` (Immune to fire damage)
*   **`slice`**: `0.4` (Takes 40% damage from slicing attacks)
*   **`holy`**: `1.2` (Takes 120% damage from holy attacks)

## Visuals (`SpriteComponent`)

The Slime Spirit has a distinct glowing, emissive appearance.

*   **`image_file`**: `data/enemies_gfx/slimespirit.xml` (References the sprite definition)
*   **`additive`**: `1` (Uses additive blending for a glowing effect)
*   **`emissive`**: `1` (The sprite itself emits light)

## Physics and Collision (`PathFindingComponent`, `HitboxComponent`, `CharacterDataComponent`)

Configuration for movement, collision detection, and physical properties.

*   **`PathFindingComponent`**:
    *   `can_fly`: `1` (Can navigate through the air)
    *   `can_swim_on_surface`: `1` (Can swim on the surface of liquids)
*   **`HitboxComponent`**:
    *   `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`: Defines the bounding box for hit detection.
*   **`CharacterDataComponent`**:
    *   `collision_aabb_min_x`, `collision_aabb_max_x`, `collision_aabb_min_y`, `collision_aabb_max_y`: Defines the bounding box for collision.
    *   `mass`: `1.0` (Standard mass)

## Special Effects (`GameEffectComponent`, `ParticleEmitterComponent`)

The Slime Spirit possesses a unique protective aura and emits particles.

*   **`GameEffectComponent`**:
    *   `effect`: `PROTECTION_FREEZE` (Applies a freeze protection effect)
    *   `frames`: `-1` (The effect is permanent while the entity exists)
*   **`ParticleEmitterComponent`**:
    *   `emitted_material_name`: `spark_purple` (Emits purple sparks)
    *   `gravity.y`: `0.0` (Particles are not affected by gravity)
    *   `lifetime_min`/`max`: `0.5` - `1.2` seconds (Duration of emitted particles)
    *   `count_min`/`max`: `20` - `30` (Number of particles emitted per burst)
    *   `area_circle_radius.min`/`max`: `32` - `72` (Radius of the emission area)
    *   `velocity_always_away_from_center`: `240` (Particles are strongly pushed away from the center)

## Scripting (`LuaComponent`)

A Lua script controls additional behaviors, likely related to its aura.

*   **`script_source_file`**: `data/scripts/animals/spirit_aura_slime.lua`
*   **`execute_every_n_frame`**: `101` (The script runs periodically)