---
title: Big Thundermage Entity
category: entities
---

# Big Thundermage Entity

This document details the `thundermage_big.xml` entity, which defines the behavior and appearance of the larger Thundermage enemy in Noita.

## Core Attributes

The Big Thundermage is a flying, electrically-charged enemy with both melee and ranged attack capabilities. It possesses immunity to touch magic and a unique set of resistances and vulnerabilities.

### `Entity` Attributes

| Attribute | Value | Description |
|---|---|---|
| `name` | `$animal_thundermage_big` | Unique identifier for the entity. |
| `tags` | `thundermage,touchmagic_immunity` | Tags that define its type and grant immunity to touch magic. |

### `Base` Entity Inheritance

This entity inherits core functionalities from `data/entities/base_enemy_basic.xml`.

## Key Components and Their Functions

### `AnimalAIComponent`

This component governs the AI behavior of the Big Thundermage.

| Attribute | Value | Description |
|---|---|---|
| `preferred_job` | `JobDefault` | Default job assigned to the AI. |
| `attack_melee_damage_min` | `0.4` | Minimum damage for melee attacks. |
| `attack_melee_damage_max` | `0.7` | Maximum damage for melee attacks. |
| `creature_detection_range_x` | `300` | Horizontal range for detecting creatures. |
| `creature_detection_range_y` | `300` | Vertical range for detecting creatures. |
| `food_material` | `blood` | Material it consumes for sustenance (though `needs_food` is 0). |
| `needs_food` | `0` | Indicates it does not require food to survive. |
| `sense_creatures` | `1` | Enables creature sensing. |
| `attack_ranged_enabled` | `1` | Enables ranged attacks. |
| `attack_melee_enabled` | `1` | Enables melee attacks. |
| `can_fly` | `1` | Allows the entity to fly. |
| `attack_ranged_entity_file` | `data/entities/projectiles/thunderball_line.xml` | The projectile used for ranged attacks. |
| `attack_ranged_action_frame` | `4` | Frame at which the ranged attack is initiated. |
| `attack_melee_action_frame` | `4` | Frame at which the melee attack is initiated. |
| `attack_ranged_frames_between` | `240` | Frames between consecutive ranged attacks. |
| `attack_ranged_offset_y` | `-20` | Vertical offset for ranged attack origin. |

### `DamageModelComponent`

Defines the health and damage-related properties.

| Attribute | Value | Description |
|---|---|---|
| `hp` | `20` | Hit points of the entity. |
| `ragdoll_material` | `diamond` | Material of the ragdoll upon death. |
| `blood_material` | `diamond` | Material of the blood. |
| `blood_spray_material` | `diamond` | Material of the blood spray. |
| `ragdoll_fx_forced` | `DISINTEGRATED` | Forced effect on ragdoll. |
| `healing_particle_effect_entity` | `data/entities/particles/heal_effect.xml` | Particle effect for healing. |

#### `damage_multipliers`

| Damage Type | Multiplier | Description |
|---|---|---|
| `explosion` | `0.0` | Immune to explosion damage. |
| `electricity` | `-1` | Takes no damage from electricity (effectively immune). |
| `holy` | `0.5` | Takes half damage from holy sources. |

### `SpriteComponent`

Controls the visual representation of the entity.

| Attribute | Value | Description |
|---|---|---|
| `image_file` | `data/enemies_gfx/thundermage_big.xml` | Primary sprite image file. |

### `CharacterPlatformingComponent`

Handles movement and platforming abilities.

| Attribute | Value | Description |
|---|---|---|
| `jump_velocity_y` | `-12` | Vertical velocity for jumping. |
| `run_velocity` | `18` | Horizontal movement speed. |

### `HitboxComponent`

Defines the collision boundaries of the entity.

| Attribute | Value | Description |
|---|---|---|
| `aabb_min_x` | `-6.5` | Minimum X-axis bounding box coordinate. |
| `aabb_max_x` | `6.5` | Maximum X-axis bounding box coordinate. |
| `aabb_min_y` | `-22` | Minimum Y-axis bounding box coordinate. |
| `aabb_max_y` | `3` | Maximum Y-axis bounding box coordinate. |

### `ElectricChargeComponent`

Manages electrical charge properties.

| Attribute | Value | Description |
|---|---|---|
| `charge_time_frames` | `2` | Frames required to build up charge. |
| `electricity_emission_interval_frames` | `8` | Frames between electrical emissions. |

### `LightComponent`

Adds a light source to the entity.

| Attribute | Value | Description |
|---|---|---|
| `r` | `120` | Red component of the light color. |
| `g` | `180` | Green component of the light color. |
| `b` | `220` | Blue component of the light color. |
| `radius` | `64` | Radius of the light emission. |

### `SpriteComponent` (Emissive)

Handles the emissive sprite for visual effects.

| Attribute | Value | Description |
|---|---|---|
| `image_file` | `data/enemies_gfx/thundermage_big_emissive.xml` | Emissive sprite image file. |
| `emissive` | `1` | Enables emissive properties. |
| `additive` | `1` | Uses additive blending for the emissive sprite. |

### `AudioLoopComponent`

Manages looping sound effects.

| Attribute | Value | Description |
|---|---|---|
| `file` | `data/audio/Desktop/animals.bank` | Audio bank file. |
| `event_name` | `animals/thundermage/movement_loop` | Name of the audio event to play. |
| `auto_play` | `1` | Starts playing automatically. |

### `LuaComponent`

Executes Lua scripts for custom behavior.

| Attribute | Value | Description |
|---|---|---|
| `script_death` | `data/scripts/animals/thundermage_big_death.lua` | Lua script executed on death. |

## Particle Emitters

The entity utilizes several particle emitters for visual effects.

### `SpriteParticleEmitterComponent` (General Sparks)

| Attribute | Value | Description |
|---|---|---|
| `sprite_file` | `data/particles/spark_electric.xml` | Sprite file for the emitted particles. |
| `emission_interval_min_frames` | `5` | Minimum frames between particle emissions. |
| `emission_interval_max_frames` | `10` | Maximum frames between particle emissions. |
| `count_min` | `1` | Minimum particles emitted per interval. |
| `count_max` | `1` | Maximum particles emitted per interval. |
| `randomize_rotation.min` | `-3.1415` | Minimum random rotation. |
| `randomize_rotation.max` | `3.1415` | Maximum random rotation. |
| `randomize_position.min_x` | `-6` | Minimum X-axis position randomization. |
| `randomize_position.max_x` | `6` | Maximum X-axis position randomization. |
| `randomize_position.min_y` | `-12` | Minimum Y-axis position randomization. |
| `randomize_position.max_y` | `2` | Maximum Y-axis position randomization. |

### `Entity` with `Base file="data/entities/base_torch_particle.xml"` (Body Particles)

This section defines particles originating from the entity's body, likely for visual flair. It includes multiple `ParticleEmitterComponent` instances with varying colors and emitted materials like `plasma_fading` and `fire_blue`.

### `Entity` for `hand_l` (Hand Particles)

This defines particles associated with the left hand (`hand_l`), also using `base_torch_particle.xml` and various `ParticleEmitterComponent` configurations for visual effects during attacks or idle states.

## Other Components

*   **`ItemChestComponent`**: Indicates the entity can drop loot (level 2).
*   **`PathFindingComponent`**: Enables pathfinding capabilities.
*   **`PathFindingGridMarkerComponent`**: Marks the entity on the pathfinding grid.
*   **`GenomeDataComponent`**: Defines its place in the ecosystem (`herd_id="mage"`, `food_chain_rank="6"`, `is_predator="1"`).
*   **`CameraBoundComponent`**: Manages camera behavior related to the entity.
*   **`CharacterDataComponent`**: Core character data, including mass and collision properties.
*   **`GameEffectComponent`**: Applies `PROTECTION_FREEZE` and `PROTECTION_ELECTRICITY` effects to the entity itself.
*   **`HotspotComponent`**: Defines a hotspot named "hand" for attachment points.