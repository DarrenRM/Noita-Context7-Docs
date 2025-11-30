---
title: Lurker Entity
category: entities
---

# Lurker Entity

This document details the configuration of the Lurker enemy entity in Noita, focusing on its combat behavior, physical attributes, and visual representation.

## Core Components

The Lurker entity is built upon a `Base` entity, inheriting common properties of flying enemies. Key components and their significant attributes are outlined below.

### Base Entity Configuration

The Lurker inherits from `data/entities/base_enemy_flying.xml`.

### AnimalAIComponent

This component governs the Lurker's artificial intelligence and combat actions.

| Attribute                 | Value                                     | Description                                                                 |
| :------------------------ | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `attack_ranged_entity_file` | `data/entities/projectiles/lurkershot.xml` | Specifies the projectile entity used for ranged attacks.                    |
| `attack_ranged_enabled`   | `1`                                       | Enables ranged attacks.                                                     |
| `attack_ranged_frames_between` | `70`                                      | Cooldown in frames between ranged attacks.                                  |
| `attack_ranged_max_distance` | `160`                                     | Maximum distance at which the Lurker can perform a ranged attack.           |
| `can_fly`                 | `1`                                       | Allows the Lurker to fly.                                                   |
| `needs_food`              | `0`                                       | The Lurker does not require food to survive.                                |

### DamageModelComponent

Defines the Lurker's health, resistances, and how it reacts to damage.

| Attribute                   | Value                                       | Description                                                                 |
| :-------------------------- | :------------------------------------------ | :-------------------------------------------------------------------------- |
| `hp`                        | `6.75`                                      | The Lurker's hit points.                                                    |
| `minimum_knockback_force`   | `100000`                                    | A very high value, indicating strong resistance to knockback.               |
| `ragdoll_fx_forced`         | `DISINTEGRATED`                             | The visual effect applied when the Lurker is defeated.                      |
| `ragdoll_material`          | `material_darkness`                         | The material associated with the Lurker's ragdoll.                          |
| `blood_material`            | `material_darkness`                         | The material of the blood it spills.                                        |
| `fire_probability_of_ignition` | `0`                                         | Cannot be ignited by fire.                                                  |
| `materials_that_damage`     | `lava,poison,blood_cold,blood_cold_vapour`  | Materials that inflict damage to the Lurker.                                |
| `materials_how_much_damage` | `0.004,0.001,0.0008,0.0007`                 | The amount of damage taken from the corresponding `materials_that_damage`.  |

#### Damage Multipliers

| Damage Type | Multiplier |
| :---------- | :--------- |
| `radioactive` | `0.0`      |
| `slice`       | `0.0`      |
| `melee`       | `0.0`      |

### SpriteComponent

Controls the visual appearance of the Lurker.

| Attribute   | Value                           | Description                               |
| :---------- | :------------------------------ | :---------------------------------------- |
| `image_file` | `data/enemies_gfx/lurker.xml`   | Path to the Lurker's sprite definition.   |
| `additive`  | `1`                             | Enables additive blending for the sprite. |

### HitboxComponent

Defines the collision boundaries for the Lurker.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_min_x` | `-6.0` | Minimum X-coordinate of the bounding box. |
| `aabb_max_x` | `6.0`  | Maximum X-coordinate of the bounding box. |
| `aabb_min_y` | `-8`   | Minimum Y-coordinate of the bounding box. |
| `aabb_max_y` | `6`    | Maximum Y-coordinate of the bounding box. |
| `is_enemy`  | `1`   | Marks this as an enemy entity.            |

### CharacterDataComponent

Provides character-specific properties like mass and collision dimensions.

| Attribute            | Value | Description                                       |
| :------------------- | :---- | :------------------------------------------------ |
| `collision_aabb_min_x` | `-6.0` | Minimum X-coordinate for collision detection.     |
| `collision_aabb_max_x` | `6.0`  | Maximum X-coordinate for collision detection.     |
| `collision_aabb_min_y` | `-8`   | Minimum Y-coordinate for collision detection.     |
| `collision_aabb_max_y` | `6`    | Maximum Y-coordinate for collision detection.     |
| `mass`               | `0.9` | The mass of the Lurker, affecting physics.        |

## Special Components

### AreaDamageComponent

This component allows the Lurker to inflict damage to entities within a specific area around it.

| Attribute        | Value      | Description                                                              |
| :--------------- | :--------- | :----------------------------------------------------------------------- |
| `aabb_min.x`     | `-10`      | Minimum X-offset for the damage area.                                    |
| `aabb_min.y`     | `-10`      | Minimum Y-offset for the damage area.                                    |
| `aabb_max.x`     | `10`       | Maximum X-offset for the damage area.                                    |
| `aabb_max.y`     | `10`       | Maximum Y-offset for the damage area.                                    |
| `damage_per_frame` | `0.10`     | Damage dealt per frame to entities within the area.                      |
| `update_every_n_frame` | `6`        | How often the damage is applied (every 6 frames).                        |
| `entities_with_tag` | `prey`     | Only applies damage to entities tagged as "prey".                        |
| `damage_type`    | `DAMAGE_CURSE` | The type of damage inflicted (curse damage).                             |

### LuaComponent

Integrates custom Lua scripting for additional behavior.

| Attribute     | Value                               | Description                                                              |
| :------------ | :---------------------------------- | :----------------------------------------------------------------------- |
| `script_shot` | `data/scripts/animals/lurkershot_start.lua` | The Lua script executed to initiate a shot action.                       |

### AudioComponent

Manages the sound effects associated with the Lurker.

| Attribute   | Value                     | Description                               |
| :---------- | :------------------------ | :---------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank` | The audio bank containing Lurker sounds.  |
| `event_root` | `animals/slimeshooter`    | The root event name for Lurker audio.     |

### GameEffectComponent

Applies a persistent game effect to the Lurker.

| Attribute | Value           | Description                               |
| :-------- | :-------------- | :---------------------------------------- |
| `effect`  | `PROTECTION_MELEE` | Grants immunity to melee damage.          |
| `frames`  | `-1`            | The effect is permanent (-1 frames).      |