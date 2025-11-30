---
title: Miniblob Entity Configuration
category: entities
---

# Miniblob Entity Configuration

This document details the configuration of the Miniblob entity in Noita, focusing on key attributes relevant for AI-assisted modding.

## Entity Definition

The Miniblob is defined as an enemy entity with specific AI behaviors, combat capabilities, and visual representation.

```xml
<Entity name="$animal_miniblob" >
  <!-- ... other components ... -->
</Entity>
```

## Base Enemy Configuration

The Miniblob inherits from `base_enemy_basic.xml`, providing a foundation for its enemy properties.

### AnimalAIComponent

This component governs the Miniblob's artificial intelligence and behavior.

| Attribute                     | Value      | Description                                                                 |
| :---------------------------- | :--------- | :-------------------------------------------------------------------------- |
| `_enabled`                    | `1`        | Enables the AI component.                                                   |
| `preferred_job`               | `JobDefault` | The default job assigned to this creature.                                  |
| `escape_if_damaged_probability` | `100`      | Probability (0-100) of escaping when damaged.                               |
| `attack_melee_damage_min`     | `0.05`     | Minimum damage dealt by melee attacks.                                      |
| `attack_melee_damage_max`     | `0.1`      | Maximum damage dealt by melee attacks.                                      |
| `creature_detection_range_x`  | `300`      | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`  | `300`      | Vertical range for detecting creatures.                                     |
| `food_material`               | `rotten_meat` | The material this creature considers food.                                  |
| `needs_food`                  | `0`        | Whether the creature requires food to survive (0 = no).                     |
| `sense_creatures`             | `1`        | Enables sensing of other creatures.                                         |
| `can_fly`                     | `1`        | Allows the creature to fly.                                                 |
| `attack_melee_enabled`        | `1`        | Enables melee attacks.                                                      |
| `attack_melee_max_distance`   | `10`       | Maximum distance for melee attacks.                                         |
| `attack_ranged_enabled`       | `0`        | Disables ranged attacks.                                                    |
| `aggressiveness_min`          | `50`       | Minimum aggressiveness level.                                               |
| `aggressiveness_max`          | `100`      | Maximum aggressiveness level.                                               |
| `attack_dash_enabled`         | `1`        | Enables a dash attack.                                                      |
| `attack_dash_distance`        | `120`      | Distance of the dash attack.                                                |

### DamageModelComponent

Defines the health and damage-related properties of the Miniblob.

| Attribute                     | Value      | Description                                                                 |
| :---------------------------- | :--------- | :-------------------------------------------------------------------------- |
| `hp`                          | `0.35`     | Hit points of the Miniblob.                                                 |
| `materials_create_messages`   | `1`        | Whether material interactions create messages.                              |
| `ragdoll_filenames_file`      | `data/ragdolls/miniblob/filenames.txt` | Path to the file defining ragdoll sprites.                                |
| `fire_probability_of_ignition`| `0`        | Probability of igniting from fire.                                          |
| `materials_damage`            | `0`        | Whether materials inflict damage on contact.                                |
| `blood_sprite_directional`    | `data/particles/bloodsplatters/bloodsplatter_directional_$[1-3].xml` | Path to directional blood splatter particle effects.                      |
| `blood_sprite_large`          | `data/particles/bloodsplatters/bloodsplatter_$[1-3].xml` | Path to large blood splatter particle effects.                           |

### SpriteComponent

Determines the visual appearance of the Miniblob.

| Attribute   | Value                                | Description                                     |
| :---------- | :----------------------------------- | :---------------------------------------------- |
| `image_file`| `data/enemies_gfx/miniblob.xml`      | Path to the primary sprite definition file.     |
| `offset_x`  | `0`                                  | Horizontal offset for the sprite.               |
| `offset_y`  | `0`                                  | Vertical offset for the sprite.                 |

### PathFindingComponent

Configures how the Miniblob navigates the game world.

| Attribute                   | Value | Description                                     |
| :-------------------------- | :---- | :---------------------------------------------- |
| `can_jump`                  | `1`   | Allows the creature to jump.                    |
| `can_fly`                   | `1`   | Allows the creature to fly.                     |
| `jump_speed`                | `100` | Speed of jumping.                               |
| `initial_jump_lob`          | `1`   | Controls the arc of the jump.                   |
| `initial_jump_max_distance_x`| `100` | Maximum horizontal distance of a jump.          |
| `initial_jump_max_distance_y`| `100` | Maximum vertical distance of a jump.            |

### PathFindingGridMarkerComponent

Used for pathfinding grid calculations.

| Attribute       | Value | Description                                     |
| :-------------- | :---- | :---------------------------------------------- |
| `marker_work_flag`| `24`  | Flag used for pathfinding grid marking.         |

### GenomeDataComponent

Provides genetic information for the creature, influencing its role in the ecosystem.

| Attribute         | Value   | Description                                     |
| :---------------- | :------ | :---------------------------------------------- |
| `herd_id`         | `slimes`| Identifier for the creature's herd or type.     |
| `food_chain_rank` | `9`     | Rank in the food chain.                         |
| `is_predator`     | `1`     | Indicates if the creature is a predator.        |

### CharacterPlatformingComponent

Defines movement characteristics for characters.

| Attribute     | Value | Description                                     |
| :------------ | :---- | :---------------------------------------------- |
| `jump_velocity_y`| `-14` | Vertical velocity applied when jumping.         |
| `run_velocity`| `25`  | Horizontal movement speed.                      |

### CameraBoundComponent

Manages how the entity interacts with the camera's view.

| Attribute   | Value   | Description                                     |
| :---------- | :------ | :---------------------------------------------- |
| `max_count` | `30`    | Maximum number of this entity that can be active. |
| `distance`  | `160000`| Distance threshold for camera relevance.        |

### HitboxComponent

Defines the collision area for the Miniblob.

| Attribute   | Value | Description                                     |
| :---------- | :---- | :---------------------------------------------- |
| `_enabled`  | `1`   | Enables the hitbox.                             |
| `aabb_min_x`| `-3`  | Minimum X-coordinate of the bounding box.       |
| `aabb_min_y`| `-4`  | Minimum Y-coordinate of the bounding box.       |
| `aabb_max_x`| `3`   | Maximum X-coordinate of the bounding box.       |
| `aabb_max_y`| `3`   | Maximum Y-coordinate of the bounding box.       |

### CharacterDataComponent

Core data for character entities.

| Attribute             | Value | Description                                     |
| :-------------------- | :---- | :---------------------------------------------- |
| `collision_aabb_min_x`| `-1.5`| Minimum X-coordinate for collision detection.   |
| `collision_aabb_max_x`| `1.5` | Maximum X-coordinate for collision detection.   |
| `collision_aabb_min_y`| `-3`  | Minimum Y-coordinate for collision detection.   |
| `collision_aabb_max_y`| `3`   | Maximum Y-coordinate for collision detection.   |
| `mass`                | `0.3` | Mass of the character.                          |

## Additional Sprite Component

This component defines an emissive sprite, likely for visual effects or animations.

| Attribute         | Value                                | Description                                     |
| :---------------- | :----------------------------------- | :---------------------------------------------- |
| `_tags`           | `character`                          | Tags associated with this sprite.               |
| `_enabled`        | `1`                                  | Enables the sprite.                             |
| `alpha`           | `1`                                  | Opacity of the sprite.                          |
| `image_file`      | `data/enemies_gfx/miniblob_emissive.xml` | Path to the emissive sprite definition file.    |
| `offset_x`        | `0`                                  | Horizontal offset for the sprite.               |
| `offset_y`        | `0`                                  | Vertical offset for the sprite.                 |
| `emissive`        | `1`                                  | Makes the sprite emissive.                      |
| `additive`        | `1`                                  | Uses additive blending for the sprite.          |
| `next_rect_animation`| `""`                                 | Name of the next animation state.               |
| `rect_animation`  | `walk`                               | Current rectangle animation state.              |

## Audio Component

Configures the sound effects associated with the Miniblob.

| Attribute   | Value                         | Description                                     |
| :---------- | :---------------------------- | :---------------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank` | Path to the audio bank file.                    |
| `event_root`| `animals/blob_small`          | Root event name for sounds related to this entity. |
```