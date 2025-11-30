---
title: Walleye Entity Configuration
category: entities
---

# Walleye Entity Configuration

This document details the configuration of the "Walleye" entity in Noita, focusing on its AI behavior, visual representation, and unique properties.

## Core Entity Properties

The Walleye is a non-player entity with specific AI behaviors and resistances.

*   **Tags:** `glue_NOT`, `polymorphable_NOT`, `curse_NOT` - These tags indicate that the Walleye cannot be glued, polymorphed, or cursed.

## AI and Behavior (`AnimalAIComponent`)

The `AnimalAIComponent` governs the Walleye's actions and interactions.

*   **`_enabled`**: `1` - The AI component is active.
*   **`preferred_job`**: `JobDefault` - The default job assigned to this creature.
*   **`escape_if_damaged_probability`**: `0` - The Walleye does not attempt to escape when damaged.
*   **`creature_detection_range_x` / `creature_detection_range_y`**: `200` - The range at which the Walleye can detect other creatures.
*   **`attack_ranged_min_distance` / `attack_ranged_max_distance`**: `0` / `200` - The Walleye attacks at any range up to 200 pixels.
*   **`food_material`**: `meat` - Indicates its food source.
*   **`needs_food`**: `0` - The Walleye does not require food.
*   **`sense_creatures`**: `1` - The Walleye is capable of sensing creatures.
*   **`attack_ranged_enabled`**: `1` - The Walleye can perform ranged attacks.
*   **`attack_melee_enabled`**: `0` - The Walleye cannot perform melee attacks.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/orb_pink_big.xml` - The projectile used for its ranged attack.
*   **`attack_ranged_frames_between`**: `60` - The cooldown between ranged attacks.
*   **`aggressiveness_min` / `aggressiveness_max`**: `95` / `100` - The Walleye is highly aggressive.
*   **`is_static_turret`**: `0` - The Walleye is not a static turret.

## Damage and Health (`DamageModelComponent`)

This component defines how the Walleye handles damage.

*   **`air_needed`**: `0` - Does not require air to survive.
*   **`fire_probability_of_ignition`**: `0` - Cannot ignite from fire.
*   **`ragdoll_fx_forced`**: `DISINTEGRATED` - The visual effect upon death.
*   **`ragdoll_material`**: `rock_static_glow` - The material used for its ragdoll.

## Visuals (`SpriteComponent`)

Defines the visual appearance of the Walleye.

*   **`image_file`**: `data/buildings_gfx/walleye.xml` - The sprite file for the Walleye.
*   **`z_index`**: `1` - Controls the rendering order.

## Movement and Physics (`CharacterPlatformingComponent`, `PathFindingComponent`)

These components dictate the Walleye's movement capabilities.

*   **`CharacterPlatformingComponent`**:
    *   `jump_velocity_y`, `run_velocity`, `velocity_min_x`, `velocity_max_x`, `velocity_min_y`, `velocity_max_y`, `pixel_gravity`: All set to `0`, indicating no inherent movement or gravity.
*   **`PathFindingComponent`**:
    *   `can_jump`: `0`
    *   `can_fly`: `0`
    *   `can_walk`: `0` - The Walleye does not possess standard movement abilities like walking or jumping.

## Other Components

*   **`PathFindingGridMarkerComponent`**: `marker_work_flag="16"` - Used for pathfinding grid interactions.
*   **`GenomeDataComponent`**:
    *   `herd_id`: `ghost`
    *   `food_chain_rank`: `5`
    *   `is_predator`: `1` - Indicates it's a predator in its ecosystem.
*   **`CameraBoundComponent`**: Manages the entity's behavior relative to the camera.
*   **`HitboxComponent`**: Defines the collision area.
*   **`CharacterDataComponent`**:
    *   `collision_aabb_min_x/max_x/min_y/max_y`: Defines the collision bounding box.
    *   `mass`: `0.01` - Very low mass.

## Special Effects and Abilities

The Walleye possesses several innate resistances and a unique blinking ability.

*   **Game Effect Components**: The Walleye is immune to:
    *   Freeze (`STUN_PROTECTION_FREEZE`)
    *   Electricity (`STUN_PROTECTION_ELECTRICITY`)
    *   Knockback (`KNOCKBACK_IMMUNITY`)
    *   Projectiles (`PROTECTION_PROJECTILE`)
    These effects are applied indefinitely (`frames="-1"`).

*   **Lua Script (`LuaComponent`)**:
    *   **`script_source_file`**: `data/scripts/buildings/walleye_blink.lua` - This script controls the Walleye's blinking behavior.
    *   **`execute_every_n_frame`**: `40` - The blinking script is executed every 40 frames.