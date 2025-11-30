---
title: Necromancer Enemy Entity
category: entities
---

# Necromancer Enemy Entity

This document details the `necromancer.xml` entity, defining the attributes and behaviors of the Necromancer enemy in Noita.

## Core Attributes

The Necromancer is a flying enemy with ranged and melee attack capabilities, a moderate health pool, and a distinct visual and auditory presence.

### Base Entity Configuration

The Necromancer inherits its fundamental properties from `data/entities/base_enemy_flying.xml`.

### `AnimalAIComponent` - Behavior and Attacks

This component governs the Necromancer's artificial intelligence, including its movement and combat actions.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `attack_ranged_entity_file` | Specifies the projectile used for ranged attacks (`polyorb.xml`).        |
| `attack_ranged_enabled`   | Enables ranged attacks (1).                                              |
| `attack_dash_enabled`     | Disables dash attacks (0).                                               |
| `attack_ranged_frames_between` | Cooldown between ranged attacks (200 frames).                            |
| `attack_ranged_offset_x`  | Horizontal offset for ranged attack origin (4).                          |
| `attack_ranged_offset_y`  | Vertical offset for ranged attack origin (-6).                           |
| `attack_ranged_action_frame` | Frame within the attack animation when the projectile is fired (5).      |
| `attack_melee_enabled`    | Enables melee attacks (1).                                               |
| `attack_melee_damage_min` | Minimum damage for melee attacks (0.8).                                  |
| `attack_melee_damage_max` | Maximum damage for melee attacks (1.4).                                  |
| `attack_melee_max_distance` | Maximum distance for melee attacks (15 units).                           |
| `attack_ranged_min_distance` | Minimum distance required to initiate a ranged attack (15 units).        |
| `attack_melee_action_frame` | Frame within the attack animation when melee damage is applied (5).      |
| `needs_food`              | The Necromancer does not require food (0).                               |
| `can_fly`                 | The Necromancer is capable of flight (1).                                |

### `DamageModelComponent` - Health and Damage Resistance

Defines the Necromancer's health, how it reacts to damage, and its material properties upon death.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `hp`                      | Health points of the Necromancer (5).                                    |
| `ragdoll_material`        | Material used for the ragdoll upon death (`meat_cursed_dry`).            |
| `blood_material`          | Material of the blood particles (`bone`).                                |
| `blood_spray_material`    | Material of the blood spray particles (`bone`).                          |
| `ragdoll_filenames_file`  | Path to the file defining ragdoll sprites (`data/ragdolls/necromancer/filenames.txt`). |
| `blood_sprite_directional` | No directional blood sprites.                                            |
| `fire_probability_of_ignition` | Probability of igniting from fire (4%).                                  |
| `blood_sprite_large`      | No large blood sprites.                                                  |
| `air_needed`              | The Necromancer does not require air (0).                                |
| `damage_multipliers`      | Modifiers for incoming damage types.                                     |
| `holy`                    | Takes 1.2x damage from holy sources.                                     |

### `PathFindingComponent` - Movement Capabilities

Specifies how the entity navigates the game world.

| Attribute | Description             |
| :-------- | :---------------------- |
| `can_fly` | Can fly (1).            |
| `can_walk`| Cannot walk (0).        |

### `SpriteComponent` - Visual Representation

Defines the graphical assets used for the Necromancer.

| Attribute   | Description                                    |
| :---------- | :--------------------------------------------- |
| `image_file`| Path to the sprite definition (`data/enemies_gfx/necromancer.xml`). |
| `offset_x`  | Horizontal sprite offset (0).                  |
| `offset_y`  | Vertical sprite offset (0).                    |

### `HitboxComponent` - Collision and Interaction

Determines the physical boundaries of the Necromancer for collision detection.

| Attribute    | Description                                    |
| :----------- | :--------------------------------------------- |
| `aabb_min_x` | Minimum X-axis bounding box coordinate (-6.5). |
| `aabb_max_x` | Maximum X-axis bounding box coordinate (6.5).  |
| `aabb_min_y` | Minimum Y-axis bounding box coordinate (-16.0).|
| `aabb_max_y` | Maximum Y-axis bounding box coordinate (3).    |
| `is_enemy`   | This hitbox belongs to an enemy (1).           |
| `is_item`    | This hitbox is not an item (0).                |
| `is_player`  | This hitbox is not the player (0).             |

### `GenomeDataComponent` - Biological Classification

Assigns the Necromancer to a specific genetic group.

| Attribute | Description                                |
| :-------- | :----------------------------------------- |
| `herd_id` | Belongs to the 'mage' herd.                |

### `CharacterDataComponent` - Physical Properties

Defines general physical characteristics of the character.

| Attribute        | Description                                    |
| :--------------- | :--------------------------------------------- |
| `collision_aabb_min_x` | Minimum X-axis collision box (-5.0).       |
| `collision_aabb_max_x` | Maximum X-axis collision box (5.0).        |
| `collision_aabb_min_y` | Minimum Y-axis collision box (-16).        |
| `collision_aabb_max_y` | Maximum Y-axis collision box (3).          |
| `mass`           | Mass of the character (2.1).                 |

## Additional Components

### `LightComponent` - Illumination

Adds a light source originating from the Necromancer.

| Attribute | Description                                    |
| :-------- | :--------------------------------------------- |
| `radius`  | The radius of the light source (70).           |
| `r`       | Red component of the light color (149).        |
| `g`       | Green component of the light color (235).      |
| `b`       | Blue component of the light color (255).       |

### `AudioComponent` - Sound Effects

Manages the sound events associated with the Necromancer.

| Attribute   | Description                                    |
| :---------- | :--------------------------------------------- |
| `file`      | Path to the audio bank (`data/audio/Desktop/animals.bank`). |
| `event_root`| The root event name for Necromancer sounds (`animals/necromancer`). |

### `AudioLoopComponent` - Looping Sounds

Handles looping audio, such as movement sounds.

| Attribute     | Description                                    |
| :------------ | :--------------------------------------------- |
| `file`        | Path to the audio bank (`data/audio/Desktop/animals.bank`). |
| `event_name`  | The name of the looping sound event (`animals/wizard_slow/movement_loop`). |
| `set_speed_parameter` | Enables setting the speed parameter of the loop (1). |
| `auto_play`   | The loop starts automatically (1).             |