---
title: Thundertrap Left Entity
category: entities
---

# Thundertrap Left Entity

This document details the `thundertrap_left.xml` entity, a building entity in Noita. It functions as a stationary trap that attacks with electricity.

## Core Components

### AnimalAIComponent
Manages the AI behavior of the Thundertrap.

| Attribute                     | Value                               | Description                                                                 |
| :---------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `preferred_job`               | `JobDefault`                        | Default job assigned to the entity.                                         |
| `escape_if_damaged_probability` | `50`                                | Probability (in percent) of escaping when damaged.                          |
| `creature_detection_range_x`  | `300`                               | Horizontal range (in pixels) for detecting creatures.                       |
| `creature_detection_range_y`  | `40`                                | Vertical range (in pixels) for detecting creatures.                         |
| `creature_detection_angular_range_deg` | `10`                                | Angular range (in degrees) for creature detection.                          |
| `food_material`               | `blood`                             | Material the entity consumes for sustenance.                                |
| `needs_food`                  | `1`                                 | Whether the entity requires food to survive.                                |
| `sense_creatures`             | `1`                                 | Whether the entity can sense nearby creatures.                              |
| `attack_ranged_entity_file`   | `data/entities/projectiles/thunder_trap.xml` | The entity file used for ranged attacks.                                    |
| `attack_ranged_frames_between`| `120`                               | Number of frames to wait between ranged attacks.                            |
| `aggressiveness_min`          | `30`                                | Minimum aggressiveness level.                                               |
| `aggressiveness_max`          | `50`                                | Maximum aggressiveness level.                                               |

### DamageModelComponent
Defines the health and damage resistances of the Thundertrap.

| Attribute                 | Value   | Description                                     |
| :------------------------ | :------ | :---------------------------------------------- |
| `hp`                      | `5.5`   | Hit points of the entity.                       |
| `ragdoll_material`        | `plastic` | Material used for the ragdoll when destroyed.   |
| `blood_material`          | `sand`  | Material that acts as blood when damaged.       |
| `fire_probability_of_ignition` | `0.0`   | Probability of igniting from fire damage.       |
| `air_needed`              | `0`     | Whether the entity requires air to survive.     |

**Damage Multipliers:**

| Type       | Value |
| :--------- | :---- |
| `drill`    | `0.4` |
| `fire`     | `0.0` |
| `explosion`| `0.2` |
| `electricity`| `0.0` |

### SpriteComponent
Handles the visual representation of the Thundertrap.

| Attribute     | Value                                | Description                                     |
| :------------ | :----------------------------------- | :---------------------------------------------- |
| `image_file`  | `data/buildings_gfx/thundertrap_left.xml` | The GFX file defining the sprite's appearance. |
| `offset_x`    | `0`                                  | Horizontal offset of the sprite.                |
| `offset_y`    | `0`                                  | Vertical offset of the sprite.                  |

### PixelSceneComponent
Defines a pixel-based scene associated with the entity, likely for its visual structure.

| Attribute    | Value                                  | Description                                     |
| :----------- | :------------------------------------- | :---------------------------------------------- |
| `pixel_scene`| `data/biome_impl/crypt/trap_frame_left.png` | Path to the pixel scene file.                   |
| `offset_x`   | `-5`                                   | Horizontal offset of the pixel scene.           |
| `offset_y`   | `-10`                                  | Vertical offset of the pixel scene.             |

## Other Notable Components

*   **SpriteAnimatorComponent**: Handles sprite animations.
*   **PathFindingComponent**: Defines pathfinding parameters, though many are set to `0` indicating limited movement.
*   **GenomeDataComponent**: Assigns a `herd_id` and `food_chain_rank`, marking it as a predator.
*   **CharacterPlatformingComponent**: Controls movement properties, with all values set to `0` indicating no platforming capabilities.
*   **HitboxComponent**: Defines the bounding box for collision detection.
*   **CameraBoundComponent**: Manages how the entity interacts with the camera's bounds.
*   **GameEffectComponent**: Applies persistent game effects. In this case, it grants `STUN_PROTECTION_FREEZE` and `PROTECTION_ELECTRICITY` indefinitely (`frames="-1"`).
*   **LuaComponent**: Executes a Lua script (`crypt_trap_check.lua`) periodically (`execute_every_n_frame="120"`), likely for custom logic or trap activation.