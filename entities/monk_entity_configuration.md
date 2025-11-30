---
title: Monk Entity Configuration
category: entities
---

# Monk Entity Configuration

This document details the configuration of the Monk entity in Noita, focusing on key attributes relevant to AI-driven modding.

## Core Entity Definition

The Monk is a basic enemy type, inheriting core functionalities from `base_enemy_basic.xml`.

### Key Components and Attributes:

*   **`ItemChestComponent`**:
    *   `level`: 1 (Indicates the loot tier or complexity of items it might drop).

*   **`AnimalAIComponent`**: Governs the Monk's behavior and sensory capabilities.
    *   `can_fly`: 0 (Cannot fly).
    *   `preferred_job`: `JobDefault` (Uses standard AI job assignments).
    *   `escape_if_damaged_probability`: 35 (35% chance to attempt escape when damaged).
    *   `creature_detection_range_x`, `creature_detection_range_y`: 250 (Detects creatures within a 250-unit radius on both axes).
    *   `sense_creatures`: 1 (Actively senses nearby creatures).
    *   `attack_melee_enabled`: 0 (Cannot perform melee attacks).
    *   `attack_ranged_enabled`: 0 (Cannot perform ranged attacks).

*   **`DamageModelComponent`**: Defines the Monk's health and damage-related properties.
    *   `hp`: 7 (Has 7 hit points).
    *   `materials_create_messages`: 1 (Damaging it can trigger game messages).
    *   `ragdoll_material`: `steel` (Ragdoll is made of steel).
    *   `blood_material`: `oil` (Leaves oil when damaged).
    *   `blood_multiplier`: 0.3 (Amount of blood produced).
    *   `ragdoll_filenames_file`: `data/ragdolls/monk/filenames.txt` (Specifies ragdoll animation files).
    *   `fire_probability_of_ignition`: 0 (Cannot ignite from fire).
    *   `physics_objects_damage`: 1 (Can be damaged by physics objects).
    *   `critical_damage_resistance`: 1.0 (No special resistance to critical damage).
    *   `air_needed`: 0 (Does not require air to survive).

*   **`SpriteComponent`**: Handles visual representation.
    *   `image_file`: `data/enemies_gfx/monk.xml` (Uses a specific sprite definition file).
    *   `offset_x`, `offset_y`: 0 (No sprite offset).

*   **`PathFindingComponent`**: Controls movement and navigation.
    *   `distance_to_reach_node_x`, `distance_to_reach_node_y`: 20 (Tolerance for reaching navigation nodes).
    *   `can_swim_on_surface`: 1 (Can swim on the surface).
    *   `can_dive`: 1 (Can dive).
    *   `frames_to_get_stuck`: 30 (Takes 30 frames to be considered stuck).
    *   `can_jump`: 1 (Can jump).
    *   `jump_speed`: 80 (Jump vertical speed).
    *   `initial_jump_max_distance_x`, `initial_jump_max_distance_y`: 40, 20 (Maximum horizontal and vertical jump distances).

*   **`GenomeDataComponent`**: Defines its place in the ecosystem.
    *   `herd_id`: `robot` (Belongs to the 'robot' herd).
    *   `food_chain_rank`: 5 (Position in the food chain).
    *   `is_predator`: 1 (Is a predator).

*   **`CharacterDataComponent`**: General character physics and collision properties.
    *   `buoyancy_check_offset_y`: -4 (Vertical offset for buoyancy checks).
    *   `collision_aabb_min_x`, `collision_aabb_max_x`: -2.0, 2.0 (Horizontal collision bounds).
    *   `collision_aabb_min_y`, `collision_aabb_max_y`: -10, 0 (Vertical collision bounds).
    *   `mass`: 2.0 (Mass of the character).

*   **`CharacterPlatformingComponent`**: Specific platforming movement parameters.
    *   `pixel_gravity`: 600 (Gravity applied to the character).
    *   `jump_velocity_y`: -20 (Initial upward velocity for jumping).
    *   `run_velocity`: 18 (Horizontal movement speed).
    *   `run_animation_velocity_switching_enabled`: 1 (Enables animation switching based on velocity).
    *   `run_animation_velocity_switching_threshold`: 50 (Velocity threshold for animation switching).
    *   `swim_idle_buoyancy_coeff`: 0.8 (Buoyancy coefficient when idle in water).

*   **`HitboxComponent`**: Defines the entity's hitbox for interactions.
    *   `aabb_min_x`, `aabb_max_x`: -4.5, 4.5 (Hitbox horizontal bounds).
    *   `aabb_min_y`, `aabb_max_y`: -19, 0 (Hitbox vertical bounds).
    *   `is_enemy`: 1 (This hitbox belongs to an enemy).
    *   `is_item`: 0 (Not an item).
    *   `is_player`: 0 (Not the player).

## Attached Entities

The Monk entity also includes several attached entities for visual and functional elements.

### Arms

*   Multiple instances of `data/entities/misc/monk_arm.xml` are attached.
*   Some arms have a `SpriteComponent` with `special_scale_x="-1"` for mirroring.
*   `arm_fx` entities are attached, likely for visual effects related to the arms, referencing `data/entities/misc/monk_arm_fx.xml`.

### Cape

*   A `monk_cape.xml` entity is attached, positioned at `position.y="-12"` relative to the Monk.

### Audio Component

*   **`AudioComponent`**:
    *   `file`: `data/audio/Desktop/animals.bank` (Sound bank file).
    *   `event_root`: `animals/monk` (Root event name for Monk sounds).

### Game Effect Component

*   An attached entity with a `GameEffectComponent` grants the `PROTECTION_FREEZE` effect for `-1` frames (permanent).

---