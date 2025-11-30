---
title: Glowing Wraith Entity
category: entities
---

# Glowing Wraith Entity

This document details the configuration of the "Glowing Wraith" entity in Noita, focusing on attributes relevant to AI-assisted modding.

## Core Attributes

The Glowing Wraith is a flying, non-aggressive enemy with unique visual and damage properties.

### Base Entity Configuration

The entity inherits from `data/entities/base_enemy_flying.xml`, providing fundamental flying enemy behaviors.

### Health and Damage

*   **HP:** `14.75` - The base health of the wraith.
*   **Damage Multipliers:** The wraith has specific resistances and vulnerabilities.
    *   `projectile`: `0.1` (Highly resistant)
    *   `explosion`: `0.1` (Highly resistant)
    *   `electricity`: `0.5` (Moderately resistant)
    *   `fire`: `0.5` (Moderately resistant)
    *   `slice`: `0.1` (Highly resistant)
    *   `ice`: `0.1` (Highly resistant)
    *   `holy`: `0.1` (Highly resistant)
*   **Ragdoll/Blood FX:**
    *   `ragdoll_fx_forced`: `DISINTEGRATED` - Upon death, it disintegrates.
    *   `ragdoll_material`: `plasma_fading` - The material used for its disintegration effect.
    *   `blood_material`: `plasma_fading` - The material for its blood effect.
    *   `blood_spray_material`: `plasma_fading` - The material for its blood spray effect.
*   **Knockback:** `minimum_knockback_force="100000"` - Extremely high knockback resistance.

### AI and Movement

*   **`AnimalAIComponent`:**
    *   `attack_ranged_enabled`: `0` - Cannot perform ranged attacks.
    *   `attack_dash_enabled`: `0` - Cannot perform dash attacks.
    *   `needs_food`: `0` - Does not require food.
    *   `can_fly`: `1` - Capable of flight.
*   **`PathFindingComponent`:**
    *   `can_fly`: `1` - Pathfinding prioritizes flight.
    *   `can_walk`: `0` - Cannot walk.

### Visuals and Audio

*   **`SpriteComponent`:**
    *   `image_file`: `data/enemies_gfx/wraith_glowing.xml` - Specifies the sprite graphics.
*   **`LightComponent`:**
    *   `radius`: `30` - The radius of its emitted light.
    *   `r`, `g`, `b`: `99`, `205`, `139` - Defines a greenish-cyan light color.
*   **`AudioComponent`:**
    *   `file`: `data/audio/Desktop/animals.bank` - Sound bank for animal audio.
    *   `event_root`: `animals/wraith_glowing` - Base event name for its sounds.
*   **`AudioLoopComponent`:**
    *   `event_name`: `animals/wraith_glowing/movement_loop` - Plays a continuous movement sound.

### Collision and Hitbox

*   **`HitboxComponent`:**
    *   `aabb_min_x`, `aabb_max_x`: `-7.0`, `7.0` - Horizontal bounds of the hitbox.
    *   `aabb_min_y`, `aabb_max_y`: `-7`, `7` - Vertical bounds of the hitbox.
*   **`CharacterDataComponent`:**
    *   `collision_aabb_min_x`, `collision_aabb_max_x`: `-2.0`, `2.0` - Horizontal bounds for collision.
    *   `collision_aabb_min_y`, `collision_aabb_max_y`: `-6`, `4` - Vertical bounds for collision.
    *   `mass`: `0.9` - The mass of the character.

### Special Components

*   **`GenomeDataComponent`:**
    *   `herd_id`: `mage` - Identifies its affiliation or type.
    *   `food_chain_rank`: `15` - Its position in the food chain.
    *   `is_predator`: `1` - It is a predator.
*   **`LuaComponent`:**
    *   `script_damage_received`: `data/scripts/animals/wraith_glowing_damage.lua` - Custom script for handling damage taken.
*   **Particle Emitters:** The entity includes several `ParticleEmitterComponent` instances, primarily for visual effects like sparks and a "fog of war hole" sprite, contributing to its ethereal appearance.
*   **Cape Entity:** It has a separate `Entity` with a `Base file="data/entities/verlet_chains/wraith_cape/wraith_glowing/wraith_cape.xml"` which likely handles its cape visual.