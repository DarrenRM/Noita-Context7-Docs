---
title: Scorpion Entity Documentation
category: entities
---

# Scorpion Entity Documentation

This document details the attributes and behaviors of the Scorpion entity in Noita, useful for AI-assisted modding.

## Core Entity Definition

The Scorpion is a basic, non-aggressive creature with minimal health and no offensive capabilities. It primarily focuses on movement and detection.

```xml
<Entity tags="mortal,prey" name="$animal_scorpion">
  <Base file="data/entities/base_helpless_animal.xml" >
    <!-- ... components ... -->
  </Base>
  <AudioComponent
    file="data/audio/Desktop/animals.bank"
    event_root="animals/longleg" >
  </AudioComponent>
</Entity>
```

## Key Components and Attributes

### AnimalAIComponent

Controls the AI behavior of the scorpion.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `preferred_job`           | Set to `JobDefault`, indicating no specific AI task.                     |
| `attack_melee_enabled`    | `0` - Scorpion cannot perform melee attacks.                             |
| `attack_ranged_enabled`   | `0` - Scorpion cannot perform ranged attacks.                            |
| `sense_creatures`         | `1` - Scorpion can detect other creatures.                               |
| `creature_detection_range_x` | `128` - Horizontal range for creature detection.                         |
| `creature_detection_range_y` | `160` - Vertical range for creature detection.                           |
| `can_fly`                 | `0` - Scorpion is ground-bound.                                          |

### DamageModelComponent

Defines the health and damage-related properties.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `hp`                      | `0.1` - Extremely low health, making it very fragile.                    |
| `fire_probability_of_ignition` | `0.05` - Low chance of igniting from fire.                               |
| `ragdoll_filenames_file`  | `data/ragdolls/scorpion/filenames.txt` - Specifies ragdoll assets.       |

### SpriteComponent

Handles the visual representation of the scorpion.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `image_file`              | `data/enemies_gfx/scorpion.xml` - Points to the scorpion's sprite data.  |
| `rect_animation`          | `stand` - The default animation state.                                   |

### PathFindingComponent

Manages the scorpion's ability to navigate the environment.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `distance_to_reach_node_x` | `20` - Horizontal tolerance for reaching navigation points.              |
| `distance_to_reach_node_y` | `20` - Vertical tolerance for reaching navigation points.                |
| `frames_to_get_stuck`     | `20` - Number of frames before considering itself stuck.                 |
| `can_jump`                | `0` - Scorpion cannot jump.                                              |

### GenomeDataComponent

Provides genetic information for AI and world generation.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `herd_id`                 | `helpless` - Identifies it as part of a "helpless" group.                |
| `food_chain_rank`         | `20` - A low rank, indicating it's not a predator.                       |
| `is_predator`             | `0` - Explicitly marks it as not a predator.                             |

### CharacterDataComponent

Defines physical properties like collision and mass.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `collision_aabb_min_x`    | `-2.0` - Minimum X-axis for collision bounding box.                      |
| `collision_aabb_max_x`    | `2.0` - Maximum X-axis for collision bounding box.                       |
| `collision_aabb_min_y`    | `-1` - Minimum Y-axis for collision bounding box.                        |
| `collision_aabb_max_y`    | `3` - Maximum Y-axis for collision bounding box.                         |
| `mass`                    | `0.1` - Very low mass.                                                   |

### CharacterPlatformingComponent

Governs movement characteristics.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `jump_velocity_y`         | `0` - Cannot jump.                                                       |
| `run_velocity`            | `15` - The base movement speed.                                          |

### HitboxComponent

Defines the entity's hitbox for interactions.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `aabb_min_x`              | `-2.5` - Minimum X-axis for hitbox.                                      |
| `aabb_max_x`              | `2.5` - Maximum X-axis for hitbox.                                       |
| `aabb_min_y`              | `-1.5` - Minimum Y-axis for hitbox.                                      |
| `aabb_max_y`              | `2` - Maximum Y-axis for hitbox.                                         |

### AudioComponent

Specifies sound effects associated with the scorpion.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `file`                    | `data/audio/Desktop/animals.bank` - The audio bank file.                 |
| `event_root`              | `animals/longleg` - The root event name for scorpion sounds.             |