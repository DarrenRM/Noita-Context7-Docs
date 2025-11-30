---
title: Blob Enemy Entity
category: entities
---

# Blob Enemy Entity

This document details the configuration of the "Blob" enemy entity in Noita, focusing on key attributes relevant for AI-assisted modding.

## Core Attributes

The Blob is a basic enemy with straightforward AI, primarily focused on melee combat and evasion.

### `Base` Entity Configuration

The Blob inherits from `base_enemy_basic.xml`, which provides fundamental enemy functionalities.

### `AnimalAIComponent`

This component governs the Blob's behavior and combat capabilities.

| Attribute                     | Value                               | Description                                                                                                |
| :---------------------------- | :---------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `_enabled`                    | `1`                                 | Enables the AI component.                                                                                  |
| `preferred_job`               | `JobDefault`                        | The default job assigned to this creature.                                                                 |
| `escape_if_damaged_probability` | `100`                               | The probability (0-100) that the Blob will attempt to escape when damaged.                                 |
| `attack_melee_damage_min`     | `0.3`                               | Minimum damage dealt by melee attacks.                                                                     |
| `attack_melee_damage_max`     | `0.5`                               | Maximum damage dealt by melee attacks.                                                                     |
| `creature_detection_range_x`  | `300`                               | Horizontal range (in pixels) for detecting other creatures.                                                |
| `creature_detection_range_y`  | `300`                               | Vertical range (in pixels) for detecting other creatures.                                                  |
| `food_material`               | `rotten_meat`                       | The material the Blob considers food.                                                                      |
| `needs_food`                  | `0`                                 | Whether the Blob requires food to survive. `0` means it does not.                                            |
| `sense_creatures`             | `1`                                 | Enables the creature sensing capability.                                                                   |
| `can_fly`                     | `0`                                 | Whether the creature can fly. `0` means it cannot.                                                         |
| `attack_melee_enabled`        | `1`                                 | Enables melee attacks.                                                                                     |
| `attack_melee_max_distance`   | `10`                                | Maximum distance (in pixels) for performing a melee attack.                                                |
| `attack_ranged_enabled`       | `0`                                 | Enables ranged attacks. `0` means it does not have ranged attacks.                                         |
| `aggressiveness_min`          | `50`                                | Minimum aggressiveness level (0-100).                                                                      |
| `aggressiveness_max`          | `100`                               | Maximum aggressiveness level (0-100).                                                                      |
| `attack_dash_enabled`         | `1`                                 | Enables a dash attack.                                                                                     |
| `attack_dash_distance`        | `80`                                | The distance (in pixels) the Blob will dash when attacking.                                                |

### `DamageModelComponent`

Defines the Blob's health and how it reacts to damage.

| Attribute                     | Value                               | Description                                                                                                |
| :---------------------------- | :---------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `hp`                          | `1.5`                               | The Blob's health points.                                                                                  |
| `materials_create_messages`   | `1`                                 | Whether materials created by damage generate messages.                                                     |
| `ragdoll_filenames_file`      | `data/ragdolls/blob/filenames.txt`  | Path to the file defining the ragdoll sprites for the Blob.                                                |
| `fire_probability_of_ignition`| `0`                                 | Probability of igniting from fire. `0` means it cannot ignite.                                             |
| `materials_damage`            | `0`                                 | Whether the Blob takes damage from materials. `0` means it does not.                                        |
| `blood_sprite_directional`    | `data/particles/bloodsplatters/bloodsplatter_directional_$[1-3].xml` | Sprite files for directional blood splatters.                                                              |
| `blood_sprite_large`          | `data/particles/bloodsplatters/bloodsplatter_$[1-3].xml` | Sprite files for large blood splatters.                                                                    |

### `SpriteComponent`

Controls the visual appearance of the Blob.

| Attribute     | Value                               | Description                                                                                                |
| :------------ | :---------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `image_file`  | `data/enemies_gfx/blob.xml`         | The primary sprite file for the Blob.                                                                      |
| `offset_x`    | `0`                                 | Horizontal offset for the sprite.                                                                          |
| `offset_y`    | `0`                                 | Vertical offset for the sprite.                                                                            |

### `PathFindingComponent`

Defines how the Blob navigates the environment.

| Attribute                     | Value | Description                                                                                                |
| :---------------------------- | :---- | :--------------------------------------------------------------------------------------------------------- |
| `can_jump`                    | `1`   | Whether the Blob can jump.                                                                                 |
| `can_fly`                     | `0`   | Whether the Blob can fly.                                                                                  |
| `jump_speed`                  | `100` | The speed at which the Blob jumps.                                                                         |
| `initial_jump_lob`            | `1`   | Controls the arc of the jump.                                                                              |
| `initial_jump_max_distance_x` | `100` | Maximum horizontal distance the Blob can jump.                                                             |
| `initial_jump_max_distance_y` | `100` | Maximum vertical distance the Blob can jump.                                                               |

### `GenomeDataComponent`

Provides genetic information for creature interactions and AI.

| Attribute         | Value     | Description                                                                                                |
| :---------------- | :-------- | :--------------------------------------------------------------------------------------------------------- |
| `herd_id`         | `slimes`  | Identifier for the herd this creature belongs to.                                                          |
| `food_chain_rank` | `9`       | Rank in the food chain. Higher numbers indicate a higher position.                                         |
| `is_predator`     | `1`       | Whether this creature is a predator. `1` means it is.                                                      |

### `CharacterPlatformingComponent`

Governs the Blob's movement characteristics.

| Attribute       | Value | Description                                                                                                |
| :-------------- | :---- | :--------------------------------------------------------------------------------------------------------- |
| `jump_velocity_y` | `-14` | The vertical velocity applied when jumping. Negative values mean upward.                                   |
| `run_velocity`  | `18`  | The horizontal movement speed when running.                                                                |

### `HitboxComponent`

Defines the collision area for the Blob.

| Attribute   | Value | Description                                                                                                |
| :---------- | :---- | :--------------------------------------------------------------------------------------------------------- |
| `aabb_max_x`| `5`   | Maximum X-coordinate of the Axis-Aligned Bounding Box (AABB).                                              |
| `aabb_max_y`| `3`   | Maximum Y-coordinate of the AABB.                                                                          |
| `aabb_min_x`| `-5`  | Minimum X-coordinate of the AABB.                                                                          |
| `aabb_min_y`| `-7`  | Minimum Y-coordinate of the AABB.                                                                          |

### `CharacterDataComponent`

Provides general character data, including collision and mass.

| Attribute           | Value | Description                                                                                                |
| :------------------ | :---- | :--------------------------------------------------------------------------------------------------------- |
| `collision_aabb_min_x`| `-3.00`| Minimum X-coordinate for collision detection.                                                              |
| `collision_aabb_max_x`| `3.00` | Maximum X-coordinate for collision detection.                                                              |
| `collision_aabb_min_y`| `-5`  | Minimum Y-coordinate for collision detection.                                                              |
| `collision_aabb_max_y`| `3`   | Maximum Y-coordinate for collision detection.                                                              |
| `mass`              | `0.9` | The mass of the character, affecting physics interactions.                                                 |

## Scripted Behavior

### `LuaComponent`

This component allows for custom scripting to modify or extend the Blob's behavior.

| Attribute             | Value                                | Description                                                                                                |
| :-------------------- | :----------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `_enabled`            | `1`                                  | Enables the Lua component.                                                                                 |
| `script_damage_received`| `data/scripts/animals/blob_damage.lua` | Path to the Lua script executed when the Blob receives damage.                                             |

## Visuals and Audio

### Emissive `SpriteComponent`

This component defines an additional sprite layer, often used for visual effects like glowing.

| Attribute       | Value                                   | Description                                                                                                |
| :-------------- | :-------------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `_tags`         | `character`                             | Tags associated with this sprite component.                                                                |
| `_enabled`      | `1`                                     | Enables the sprite component.                                                                              |
| `alpha`         | `1`                                     | Opacity of the sprite (0-1).                                                                               |
| `image_file`    | `data/enemies_gfx/blob_emissive.xml`    | The sprite file for the emissive effect.                                                                   |
| `offset_x`      | `0`                                     | Horizontal offset for the sprite.                                                                          |
| `offset_y`      | `0`                                     | Vertical offset for the sprite.                                                                            |
| `emissive`      | `1`                                     | Enables emissive properties, making the sprite glow.                                                       |
| `additive`      | `1`                                     | Enables additive blending, often used for glowing effects.                                                 |
| `next_rect_animation` | `""`                                    | Name of the next animation to play. Empty means no specific next animation.                                |
| `rect_animation`| `walk`                                  | The name of the current rectangle animation to play.                                                       |

### `AudioComponent`

Manages the sound effects associated with the Blob.

| Attribute   | Value                      | Description                                                                                                |
| :---------- | :------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank` | The audio bank file containing the sound events.                                                           |
| `event_root`| `animals/blob`             | The root event name for Blob-related sounds within the audio bank.                                         |