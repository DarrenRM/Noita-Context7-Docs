---
title: Boss Limbs Entity
category: entities
---

# Boss Limbs Entity

This document details the `boss_limbs.xml` entity, a formidable boss creature in Noita. It outlines its core components, visual elements, AI behavior, physics, damage handling, and the various limbs and tentacles that constitute its form.

## Core Entity Attributes

The main entity definition sets up fundamental properties for the boss.

*   **`name`**: `$animal_boss_limbs` - The internal identifier for this entity.
*   **`tags`**: A comprehensive list of tags defining its nature and interactions: `enemy`, `mortal`, `human`, `hittable`, `homing_target`, `teleportable_NOT`, `boss`, `polymorphable_NOT`, `miniboss`, `music_energy_100`, `necrobot_NOT`, `glue_NOT`.

## Visual Components

These components define the appearance and visual effects of the Boss Limbs.

### Light Component

*   **`radius`**: `256` - The radius of the light emitted.
*   **`r`, `g`, `b`**: `100`, `255`, `130` - Defines the greenish-white color of the light.
*   **`fade_out_time`**: `1.5` - How long the light takes to fade.

### Sprite Components

These define the various visual parts of the boss.

*   **Main Body Sprite**:
    *   `image_file`: `data/entities/animals/boss_limbs/body.xml`
    *   `offset_y`: `24`
    *   `offset_x`: `24`
*   **Eye Sprites**:
    *   `image_file`: `data/entities/animals/boss_limbs/eyeA.xml` and `data/entities/animals/boss_limbs/eyeB.xml`
    *   `never_ragdollify_on_death`: `1` - Ensures eyes don't ragdoll upon death.
    *   `rect_animation`: `stand` - Specifies the animation state.
*   **Skull Sprite**:
    *   `image_file`: `data/entities/animals/boss_limbs/skull.xml`
    *   `never_ragdollify_on_death`: `1`
    *   `rect_animation`: `stand`

## AI and Behavior

This section details how the Boss Limbs perceives and interacts with the game world.

### LimbBoss Component

*   **`state`**: `1` - Likely indicates an initial active state.

### Lua Components

These components delegate complex behaviors to Lua scripts.

*   **Main Update Script**:
    *   `script_source_file`: `data/entities/animals/boss_limbs/boss_limbs_update.lua`
    *   `vm_type`: `ONE_PER_COMPONENT_INSTANCE`
    *   `enable_coroutines`: `1`
    *   `execute_on_added`: `1`
    *   `execute_every_n_frame`: `-1` (likely means every frame or controlled by script)
    *   `execute_times`: `1` (This might be a typo or specific to initial setup, as `execute_every_n_frame` suggests ongoing execution)
*   **Damage Received Script**:
    *   `script_damage_received`: `data/entities/animals/boss_limbs/boss_limbs_damage.lua`
*   **Death Script**:
    *   `script_death`: `data/entities/animals/boss_limbs/boss_limbs_death.lua`

### PathFinding Component

This component governs the entity's movement and navigation.

*   **Movement Capabilities**:
    *   `can_dive`: `1`
    *   `can_fly`: `1`
    *   `can_jump`: `0`
    *   `can_walk`: `0`
*   **Movement Parameters**:
    *   `cost_of_flying`: `500`
    *   `jump_speed`: `200`
    *   `initial_jump_max_distance_x`: `100`
    *   `initial_jump_max_distance_y`: `60`
    *   `frames_between_searches`: `20`
    *   `frames_to_get_stuck`: `120`

### PathFindingGridMarker Component

*   `marker_offset_y`: `-6` - Adjusts the marker's position relative to the entity.
*   `marker_work_flag`: `16` - A flag used by the pathfinding system.

## Physics Components

These define the physical properties and interactions of the Boss Limbs.

### PhysicsAIComponent

Controls the AI-driven physics forces.

*   **Force Parameters**:
    *   `target_vec_max_len`: `15.0`
    *   `force_coeff`: `10.0`
    *   `force_max`: `100`
    *   `torque_coeff`: `50`
    *   `torque_max`: `50.0`
*   **Deactivation**:
    *   `damage_deactivation_probability`: `0`
    *   `damage_deactivation_time_min`, `damage_deactivation_time_max`: `2` to `10`

### PhysicsBodyComponent

Defines the physical body properties.

*   `fixed_rotation`: `1` - Prevents the body from rotating freely.
*   `angular_damping`: `0.02`
*   `linear_damping`: `0`

### PhysicsShapeComponent

Defines the collision shape.

*   `is_circle`: `1` - The collision shape is a circle.
*   `radius_x`, `radius_y`: `19`
*   `friction`: `0.0`
*   `restitution`: `0.3`

## Damage and Health

This section covers how the Boss Limbs takes damage and its health properties.

### DamageModelComponent

*   **Health**:
    *   `hp`: `30`
*   **Damage Resistance/Vulnerability**:
    *   `damage_multipliers`:
        *   `melee`: `0.8`
        *   `projectile`: `0.8`
        *   `explosion`: `0.3`
        *   `electricity`: `0.9`
        *   `fire`: `1.2`
        *   `drill`: `0`
*   **Blood and Ragdoll**:
    *   `blood_material`: `slime_green`
    *   `ragdoll_material`: `meat_slime_green`
    *   `blood_sprite_directional`, `blood_sprite_large`: Specifies blood splatter particle effects.
*   **Material Interaction**:
    *   `materials_that_damage`: `acid`
    *   `materials_how_much_damage`: `0.0001`

### GenomeDataComponent

*   `food_chain_rank`: `5`
*   `herd_id`: `boss_limbs`
*   `is_predator`: `1`

### Hitbox Components

Multiple hitboxes define different areas of the boss, with varying damage multipliers.

*   **Top Hitbox**: `aabb_min_y="-20"`, `aabb_max_y="-10"`, `damage_multiplier="0"`
*   **Bottom Hitbox**: `aabb_min_y="12"`, `aabb_max_y="18"`, `damage_multiplier="0"`
*   **Center Hitbox (Default)**: `aabb_min_y="-10"`, `aabb_max_y="12"`, `damage_multiplier="0"`
*   **Center Hitbox (Weak Spot)**: `aabb_min_x="-8"`, `aabb_max_x="8"`, `aabb_min_y="-10"`, `aabb_max_y="12"`, `damage_multiplier="1.0"`

## Other Components

Miscellaneous components that add functionality.

### Audio Component

*   `file`: `data/audio/Desktop/animals.bank`
*   `event_root`: `animals` (for general sounds) and `animals/boss_limbs` (for specific boss sounds).

### SpriteAnimatorComponent

*   `target_sprite_comp_name`: `character` - Links animation to the main character sprite.

### CellEaterComponent

*   `radius`: `30`
*   `eat_probability`: `0` - This entity does not actively eat cells.

### Health Bar Components

These components render the boss's health bar.

*   `SpriteComponent` for the background (`health_bar_back`).
*   `SpriteComponent` for the foreground (`health_bar`).
*   `BossHealthBarComponent` - Manages the health bar logic.

## Sub-Entities (Limbs and Tentacles)

The Boss Limbs entity is composed of several other entities, primarily limbs and tentacles, which are instantiated using `<Base>` tags.

### Limbs

*   Multiple instances of `data/entities/animals/boss_limbs/limb.xml`.
*   One instance of `data/entities/animals/boss_limbs/limb_attacker.xml` named `limb_attacker`.

### Tentacles (Hair)

Various "hair" entities are attached with specific positional offsets.

*   **`hair3.xml`**: Used for some of the longer, thicker tentacles.
*   **`hair1.xml`**: Used for thinner, more numerous tentacles.
*   **`hair2.xml`**: Used for medium-sized tentacles.

Each tentacle entity includes an `InheritTransformComponent` to define its precise position relative to the main boss body.