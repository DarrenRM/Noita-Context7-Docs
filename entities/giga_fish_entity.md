---
title: Giga Fish Entity
category: entities
---

---

# Giga Fish Entity

This document details the Giga Fish entity, a boss-type enemy in Noita. It outlines its core attributes, physical properties, and behavioral components.

## Core Attributes

*   **`name`**: `$animal_fish_giga` - The internal identifier for this entity.
*   **`tags`**: A collection of keywords defining its behavior and interactions:
    *   `hittable`: Can be damaged by attacks.
    *   `polymorphable_NOT`: Cannot be polymorphed.
    *   `necrobot_NOT`: Immune to NecroBot effects.
    *   `glue_NOT`: Not affected by glue.
    *   `teleportable_NOT`: Cannot be teleported.
    *   `curse_NOT`: Immune to curses.
    *   `touchmagic_immunity`: Immune to magic effects that trigger on touch.
    *   `mortal`: Can be killed.
    *   `hiteffect_enabled`: Can apply hit effects.

## Physics and Movement

*   **`VelocityComponent`**:
    *   `gravity_y`: `0` - No vertical gravity applied.
    *   `air_friction`: `0` - No air resistance.
    *   `terminal_velocity`: `300` - Maximum falling speed.
    *   `displace_liquid`: `0` - Does not displace liquids.
    *   `liquid_drag`: `0` - No drag in liquids.

*   **`ProjectileComponent`**: This component is configured for bouncing and penetration, suggesting it might be used for its own projectiles or to define its interaction with the environment.
    *   `speed_min`, `speed_max`: `0` - Not directly controlled by this component.
    *   `lifetime`: `-1` - Indefinite lifetime.
    *   `bounce_always`: `1` - Always bounces.
    *   `bounces_left`: `9999999999999` - Effectively infinite bounces.
    *   `bounce_at_any_angle`: `1` - Bounces regardless of impact angle.
    *   `bounce_energy`: `0.5` - Retains half of its energy after a bounce.
    *   `penetrate_entities`: `1` - Can pass through other entities.
    *   `collide_with_world`: `0` - Does not collide with the static world geometry.

## Damage and Health

*   **`DamageModelComponent`**:
    *   `hp`: `300` - The entity's total health points.
    *   `air_needed`: `0` - Does not require air to survive.
    *   `falling_damages`: `0` - Does not take damage from falling.
    *   `blood_material`: `blood` - The material associated with its blood.
    *   `ragdoll_material`: `meat` - The material used for its ragdoll.
    *   `ragdoll_fx_forced`: `DISINTEGRATED` - The visual effect applied when ragdolling.

*   **`damage_multipliers`**: Defines how much damage it takes from different sources.
    *   `melee`: `0.01` - Takes very little melee damage.
    *   `projectile`: `0` - Immune to projectile damage.
    *   `explosion`: `0.01` - Takes very little explosion damage.
    *   `slice`: `0.01` - Takes very little slice damage.

## Biological and Behavioral Data

*   **`GenomeDataComponent`**:
    *   `food_chain_rank`: `5` - High rank in the food chain.
    *   `herd_id`: `eel` - Belongs to the "eel" group.
    *   `is_predator`: `1` - Is a predator.

## Visual Components and Structure

The Giga Fish is composed of multiple `Entity` blocks, each defining a visual part and its associated Lua script for behavior.

*   **Main Body Sprite**:
    *   `SpriteComponent` with `image_file="data/entities/animals/boss_fish/body.png"`.
    *   `offset_x="128"`, `offset_y="192"` - Position relative to the entity's origin.
    *   `z_index="2.0"` - Rendering layer.

*   **Eye Component**:
    *   `Entity` containing:
        *   `SpriteComponent` with `image_file="data/entities/animals/boss_fish/eye.xml"`.
        *   `LuaComponent` with `script_source_file="data/entities/animals/boss_fish/eye.lua"` for eye behavior.

*   **Tentacle Components**: Four separate `Entity` blocks, each for a tentacle, with their own sprites and Lua scripts for animation and interaction.

*   **Health Bar UI**:
    *   Two `SpriteComponent`s (`health_bar_back`, `health_bar`) are present for displaying the boss's health bar.
    *   `BossHealthBarComponent` enables boss-specific health bar functionality.

## Scripted Behavior

*   **`LuaComponent`**:
    *   `script_source_file="data/entities/animals/boss_fish/movement.lua"`: Handles the entity's movement logic.
    *   `script_damage_received="data/entities/animals/boss_fish/damage.lua"`: Manages how the entity reacts to taking damage.
    *   `script_death="data/entities/animals/boss_fish/death.lua"`: Defines the behavior and effects upon the entity's death.

## Protections

The Giga Fish has several built-in protections against status effects:

*   **`GameEffectComponent`**:
    *   `effect="STUN_PROTECTION_FREEZE"`: Protection against freezing.
    *   `effect="STUN_PROTECTION_ELECTRICITY"`: Protection against electricity.
    *   `effect="PROTECTION_PROJECTILE"`: Protection against projectiles.