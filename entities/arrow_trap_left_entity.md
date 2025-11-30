---
title: Arrow Trap (Left) Entity
category: entities
---

# Arrow Trap (Left) Entity

This document details the configuration of the `arrowtrap_left.xml` entity, a building entity in Noita. It functions as a stationary trap that fires projectiles.

## Key Components and Attributes

This entity is primarily defined by its AI, damage, sprite, and hitbox.

### AnimalAIComponent

Controls the behavior and targeting of the trap.

| Attribute                     | Description                                                                 |
| :---------------------------- | :-------------------------------------------------------------------------- |
| `preferred_job`               | Set to "JobDefault", indicating a standard AI behavior.                     |
| `escape_if_damaged_probability` | Probability (50%) of attempting to escape when damaged.                   |
| `attack_ranged_min_distance`  | Minimum distance (0) to engage a target with ranged attacks.                |
| `attack_ranged_max_distance`  | Maximum distance (300) to engage a target with ranged attacks.              |
| `creature_detection_range_x`  | Horizontal range (300) for detecting creatures.                             |
| `creature_detection_range_y`  | Vertical range (20) for detecting creatures.                                |
| `creature_detection_angular_range_deg` | Angular detection range (10 degrees) for creatures.                     |
| `food_material`               | The material the AI considers "food" ("blood").                             |
| `needs_food`                  | Whether the AI requires food (1 - yes).                                     |
| `sense_creatures`             | Whether the AI can sense creatures (1 - yes).                               |
| `attack_ranged_entity_file`   | The entity file for the projectile to be fired (`data/entities/projectiles/arrow.xml`). |
| `attack_ranged_frames_between`| Frames between ranged attacks (60).                                         |
| `eye_offset_x`                | Horizontal offset for the AI's "eyes" (8).                                  |
| `aggressiveness_min`          | Minimum aggressiveness level (30).                                          |
| `aggressiveness_max`          | Maximum aggressiveness level (50).                                          |

### DamageModelComponent

Defines the trap's health and how it takes damage.

| Attribute                 | Description                                     |
| :------------------------ | :---------------------------------------------- |
| `hp`                      | Health points (1.5).                            |
| `ragdoll_material`        | Material for ragdoll physics ("plastic").       |
| `blood_material`          | Material for blood effects ("sand").            |
| `fire_probability_of_ignition` | Probability of igniting from fire (0).      |
| `air_needed`              | Whether air is required for survival (0 - no).  |

#### damage_multipliers

Specific multipliers for different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `drill`     | 0.4        |
| `fire`      | 0.0        |
| `explosion` | 0.3        |

### SpriteComponent

Determines the visual appearance of the trap.

| Attribute      | Description                                  |
| :------------- | :------------------------------------------- |
| `image_file`   | Path to the sprite's graphical definition (`data/buildings_gfx/arrowtrap_left.xml`). |
| `special_scale_x` | Special scaling factor for the X-axis (1). |
| `has_special_scale` | Whether special scaling is applied (1 - yes). |
| `offset_x`     | Horizontal offset of the sprite (0).         |
| `offset_y`     | Vertical offset of the sprite (0).           |

### HitboxComponent

Defines the collision area of the trap.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `aabb_min_x`| Minimum X-coordinate of the bounding box (0). |
| `aabb_max_x`| Maximum X-coordinate of the bounding box (5). |
| `aabb_min_y`| Minimum Y-coordinate of the bounding box (-5).|
| `aabb_max_y`| Maximum Y-coordinate of the bounding box (5). |

### LuaComponent

Attaches a Lua script for custom logic.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `script_source_file`  | Path to the Lua script (`data/scripts/buildings/crypt_trap_check.lua`). |
| `execute_every_n_frame` | How often the script is executed (every 60 frames).                      |

### PixelSceneComponent

Defines a pixel-based scene associated with the entity, likely for visual effects or collision details.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `pixel_scene` | Path to the pixel scene definition (`data/biome_impl/crypt/trap_frame_left.png`). |
| `offset_x`  | Horizontal offset for the pixel scene (-5).                              |
| `offset_y`  | Vertical offset for the pixel scene (-10).                               |

## Other Components

*   **SpriteAnimatorComponent**: Handles sprite animations.
*   **PathFindingComponent**: Manages pathfinding capabilities (though largely unused for a stationary trap).
*   **GenomeDataComponent**: Provides genetic information, useful for AI herd behavior.
*   **CharacterPlatformingComponent**: Defines movement properties, set to static for this trap.
*   **CameraBoundComponent**: Controls how the entity behaves relative to the camera.
*   **Entity (with GameEffectComponent)**: Two nested entities apply "STUN\_PROTECTION\_FREEZE" and "STUN\_PROTECTION\_ELECTRICITY" effects to the trap itself, making it immune to these status effects.