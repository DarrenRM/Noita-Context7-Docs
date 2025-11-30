---
title: Wallmouth Entity
category: entities
---

# Wallmouth Entity

This document describes the `wallmouth.xml` entity, a static building entity in Noita. It functions as a defensive structure with unique behaviors and resistances.

## Key Components and Attributes

The `wallmouth.xml` entity is primarily defined by its `Base` component, which inherits from `base_enemy_basic.xml`, and several other specialized components.

### Base Component (`base_enemy_basic.xml`)

This forms the foundation of the entity's behavior, drawing from a common enemy template.

#### AnimalAIComponent

Manages the entity's artificial intelligence and combat behavior.

*   **`preferred_job`**: `JobDefault` - Indicates its default role.
*   **`creature_detection_range_x` / `creature_detection_range_y`**: `200` - Defines the detection radius for creatures.
*   **`food_material`**: `meat` - Specifies the material it's considered to be made of for AI purposes.
*   **`needs_food`**: `0` - The entity does not require food.
*   **`sense_creatures`**: `1` - Actively senses nearby creatures.
*   **`attack_ranged_enabled`**: `0` - Cannot perform ranged attacks.
*   **`attack_melee_enabled`**: `1` - Capable of melee attacks.
*   **`aggressiveness_min` / `aggressiveness_max`**: `95` / `100` - Highly aggressive.
*   **`attack_melee_max_distance`**: `16` - Maximum range for melee attacks.
*   **`attack_melee_damage_min` / `attack_melee_damage_max`**: `1.2` / `1.6` - Damage range for melee attacks.

#### DamageModelComponent

Handles damage and destruction properties.

*   **`ragdoll_filenames_file`**: `""` - No specific ragdoll files are used.
*   **`fire_probability_of_ignition`**: `0` - Cannot be ignited by fire.
*   **`ragdoll_fx_forced`**: `DISINTEGRATED` - The visual effect upon destruction.
*   **`ragdoll_material`**: `rock_static_glow` - The material associated with its destroyed form.

#### SpriteComponent

Defines the visual representation of the entity.

*   **`image_file`**: `data/buildings_gfx/wallmouth.xml` - Points to the graphical definition.
*   **`z_index`**: `1` - Controls rendering order.

#### PathFindingGridMarkerComponent

Marks the entity's presence on the pathfinding grid.

*   **`marker_work_flag`**: `16` - A flag indicating its role or type on the grid.

#### GenomeDataComponent

Provides genetic information for AI and world generation.

*   **`herd_id`**: `ghost` - Identifies its group or type.
*   **`food_chain_rank`**: `5` - Its position in the food chain.
*   **`is_predator`**: `1` - It is a predator.

#### CharacterPlatformingComponent

Defines movement and physics properties.

*   **`jump_velocity_y`**, **`run_velocity`**, **`velocity_min_x`**, **`velocity_max_x`**, **`velocity_min_y`**, **`velocity_max_y`**: All set to `0` - The entity is static and does not move.
*   **`pixel_gravity`**: `0` - No gravity applied.

#### PathFindingComponent

Determines pathfinding capabilities.

*   **`can_jump`**, **`can_fly`**, **`can_walk`**: All set to `0` - It cannot navigate the environment.

#### CameraBoundComponent

Manages entity behavior relative to the camera.

*   **`max_count`**: `30` - Limits the number of these entities that can be active.
*   **`distance`**: `160000` - The distance from the camera at which it becomes inactive.

#### HitboxComponent

Defines the collision area.

*   **`aabb_max_x`**, **`aabb_max_y`**, **`aabb_min_x`**, **`aabb_min_y`**: All set to `0` - Indicates a non-standard or minimal hitbox definition, likely handled by `CharacterDataComponent`.

#### CharacterDataComponent

Core character properties.

*   **`collision_aabb_min_x` / `max_x`**: `-3.0` / `3.0` - Defines the horizontal collision bounds.
*   **`collision_aabb_min_y` / `max_y`**: `-6` / `3` - Defines the vertical collision bounds.
*   **`mass`**: `0.01` - Very low mass.

### Additional Entities

The `wallmouth.xml` entity also contains several nested `Entity` blocks, each applying specific `GameEffectComponent`s. These grant passive immunities.

#### GameEffectComponent (Multiple Instances)

These components grant the Wallmouth various resistances.

*   **`effect`**: `STUN_PROTECTION_FREEZE`, `STUN_PROTECTION_ELECTRICITY`, `PROTECTION_PROJECTILE`, `KNOCKBACK_IMMUNITY`
*   **`frames`**: `-1` (Indicates permanent effect)

### LuaComponent

This component links the entity to a custom script for dynamic behavior.

*   **`script_source_file`**: `data/scripts/buildings/wallmouth_yawn.lua` - The script controlling its unique actions.
*   **`execute_every_n_frame`**: `60` - The script is executed every 60 frames.

## Summary

The Wallmouth is a stationary, aggressive building entity designed for defense. It possesses strong melee capabilities and is immune to freezing, electricity, projectiles, and knockback. Its primary interactive behavior is driven by the `wallmouth_yawn.lua` script, suggesting it might have a unique animation or attack pattern related to "yawning." Its static nature and lack of movement capabilities indicate it's meant to be placed strategically.