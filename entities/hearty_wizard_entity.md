---
title: Hearty Wizard Entity
category: entities
---

# Hearty Wizard Entity

This document details the `wizard_hearty.xml` entity, a flying, ranged-attacking creature in Noita.

## Core Attributes

The Hearty Wizard is a flying enemy with a ranged attack and a unique material conversion ability.

### `Base` Entity

Inherits fundamental properties from `base_enemy_basic.xml`.

### `AnimalAIComponent`

Controls the creature's behavior and senses.

*   **`creature_detection_range_x` / `creature_detection_range_y`**: Sets the detection radius for other creatures (400 units).
*   **`food_material`**: Specifies "blood" as its food source.
*   **`needs_food`**: Set to "0", indicating it does not require sustenance.
*   **`sense_creatures`**: Enabled ("1") to detect other creatures.
*   **`attack_ranged_enabled`**: Set to "1", allowing ranged attacks.
*   **`can_fly`**: Enabled ("1") for flight capabilities.
*   **`attack_ranged_entity_file`**: Points to `data/entities/projectiles/orb_hearty.xml` for its projectile.
*   **`attack_ranged_frames_between`**: Defines the delay between ranged attacks (110 frames).
*   **`attack_ranged_max_distance`**: Maximum range for its ranged attack (300 units).

### `DamageModelComponent`

Manages health and damage resistances.

*   **`hp`**: Has 12 hit points.
*   **`ragdoll_material`**: Uses "meat_confusion" for its ragdoll effect.
*   **`damage_multipliers`**:
    *   `explosion`: -0.5 (50% resistance)
    *   `electricity`: -0.5 (50% resistance)
    *   `ice`: -0.5 (50% resistance)

### `SpriteComponent`

Defines the visual appearance.

*   **`image_file`**: `data/enemies_gfx/wizard_hearty.xml`

### `CharacterPlatformingComponent`

Governs movement and physics.

*   **`run_velocity`**: Movement speed when running (18 units).
*   **`fly_velocity_x`**: Horizontal flight speed (56 units).
*   **`accel_x`**: Horizontal acceleration (0.09 units).

### `HitboxComponent`

Defines the collision area for interactions.

*   **`aabb_min_x` / `aabb_max_x`**: Horizontal bounds (-4.5 to 4.5).
*   **`aabb_min_y` / `aabb_max_y`**: Vertical bounds (-10 to 3).

### `MagicConvertMaterialComponent`

Grants a unique material transformation ability.

*   **`from_material`**: Converts "rock_box2d_hard".
*   **`to_material`**: Transforms into "air".
*   **`radius`**: The area of effect for conversion (15 units).
*   **`loop`**: Set to "1", indicating continuous conversion.

## Visual and Audio Elements

### `SpriteParticleEmitterComponent`

Emits particles for visual effects.

*   **`sprite_file`**: `data/particles/darkflame_red.xml`
*   **`lifetime`**: Particles last for 2 seconds.
*   **`gravity.y`**: Particles are affected by gravity (30 units).
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Particles are emitted every 5-10 frames.
*   **`count_min` / `count_max`**: Emits 1 particle per emission.

### `AudioLoopComponent`

Plays a looping sound for movement.

*   **`event_name`**: "animals/wizard/movement_loop"

### `AudioComponent`

Handles general sound events for the wizard.

*   **`event_root`**: "animals/wizard"

### `Entity name="cape"`

Attaches a cape visual element with physics.

*   **`VerletPhysicsComponent`**: Defines the cape's appearance and physics properties.
    *   `cloth_color_edge`: "0xFFefe08c"
    *   `cloth_color`: "0xFF7d3640"

## Other Components

### `ItemChestComponent`

Indicates the entity can drop loot (level 2).

### `PathFindingComponent`

Enables pathfinding capabilities, including jumping.

### `PathFindingGridMarkerComponent`

Marks the entity's presence on the pathfinding grid.

### `GenomeDataComponent`

Provides genetic information.

*   **`herd_id`**: "mage"
*   **`food_chain_rank`**: 6
*   **`is_predator`**: "1"

### `CameraBoundComponent`

Manages how the camera follows the entity.

### `CharacterDataComponent`

Defines collision bounds for the character.

*   **`collision_aabb_min_x` / `collision_aabb_max_x`**: Horizontal collision bounds (-3.0 to 3.0).
*   **`collision_aabb_min_y` / `collision_aabb_max_y`**: Vertical collision bounds (-7 to 3).

### `ItemPickUpperComponent`

Allows the entity to pick up items.

### `HotspotComponent`

Defines a specific point for attaching other entities (e.g., the cape).

*   **`sprite_hotspot_name`**: "cape"