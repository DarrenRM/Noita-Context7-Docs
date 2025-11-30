---
title: Firetrap Left Entity
category: entities
---

# Firetrap Left Entity

This document details the `firetrap_left.xml` entity, a building entity in Noita.

## Core Components

This entity is primarily defined by its AI, damage, sprite, and hitbox.

### AnimalAIComponent

Controls the behavior and detection capabilities of the firetrap.

| Attribute                      | Value   | Description                                                                 |
| :----------------------------- | :------ | :-------------------------------------------------------------------------- |
| `preferred_job`                | `JobDefault` | The default job assigned to this entity.                                    |
| `escape_if_damaged_probability`| `50`    | Probability (in %) of escaping when damaged.                                |
| `creature_detection_range_x`   | `300`   | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`   | `50`    | Vertical range for detecting creatures.                                     |
| `creature_detection_angular_range_deg` | `10` | Angular range (in degrees) for creature detection.                          |
| `food_material`                | `blood` | The material this entity considers food.                                    |
| `needs_food`                   | `1`     | Whether this entity requires food to survive.                               |
| `sense_creatures`              | `1`     | Whether this entity can sense nearby creatures.                             |
| `attack_ranged_entity_file`    | `data/entities/projectiles/fire_trap.xml` | The entity file used for ranged attacks (projectile).                     |
| `attack_ranged_frames_between` | `30`    | Number of frames to wait between ranged attacks.                            |
| `aggressiveness_min`           | `30`    | Minimum aggressiveness level.                                               |
| `aggressiveness_max`           | `50`    | Maximum aggressiveness level.                                               |

### DamageModelComponent

Defines the health and damage resistances of the firetrap.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `hp`                      | `4.5`   | Hit points of the entity.                                                   |
| `ragdoll_material`        | `plastic` | The material of the ragdoll when the entity is destroyed.                   |
| `blood_material`          | `sand`  | The material that spills out as "blood" when damaged.                       |
| `fire_probability_of_ignition` | `0.0` | Probability of igniting from fire damage.                                   |
| `air_needed`              | `0`     | Whether the entity requires air to survive.                                 |

#### damage_multipliers

Specific multipliers for different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `drill`     | `0.4`      |
| `fire`      | `0.0`      |
| `explosion` | `0.2`      |
| `electricity`| `0.1`      |

### SpriteComponent

Specifies the visual representation of the firetrap.

| Attribute     | Value                               | Description                                     |
| :------------ | :---------------------------------- | :---------------------------------------------- |
| `image_file`  | `data/buildings_gfx/firetrap_left.xml` | The XML file defining the sprite's appearance. |
| `special_scale_x` | `1`                                 | Horizontal scaling factor.                      |
| `has_special_scale` | `1`                                 | Enables special scaling.                        |

### HitboxComponent

Defines the collision area of the firetrap.

| Attribute   | Value | Description                                     |
| :---------- | :---- | :---------------------------------------------- |
| `aabb_min_x`| `0`   | Minimum X-coordinate of the bounding box.       |
| `aabb_max_x`| `5`   | Maximum X-coordinate of the bounding box.       |
| `aabb_min_y`| `-5`  | Minimum Y-coordinate of the bounding box.       |
| `aabb_max_y`| `5`   | Maximum Y-coordinate of the bounding box.       |

## Other Notable Components

### LuaComponent

This component allows for custom scripting to control entity behavior.

| Attribute           | Value                                  | Description                                     |
| :------------------ | :------------------------------------- | :---------------------------------------------- |
| `script_source_file`| `data/scripts/buildings/crypt_trap_check.lua` | The Lua script file to execute.                 |
| `execute_every_n_frame` | `30`                                   | How often the script is executed (in frames). |

### PixelSceneComponent

Defines a pixel-based visual overlay or interaction area.

| Attribute   | Value                                   | Description                                     |
| :---------- | :-------------------------------------- | :---------------------------------------------- |
| `pixel_scene`| `data/biome_impl/crypt/trap_frame_left.png` | The PNG file defining the pixel scene.          |
| `offset_x`  | `-4`                                    | Horizontal offset for the pixel scene.          |
| `offset_y`  | `-10`                                   | Vertical offset for the pixel scene.            |

### GameEffectComponent

Applies specific game effects to the entity.

*   **Effect:** `STUN_PROTECTION_FREEZE`
    *   **frames:** `-1` (Indicates permanent effect)
*   **Effect:** `STUN_PROTECTION_ELECTRICITY`
    *   **frames:** `-1` (Indicates permanent effect)