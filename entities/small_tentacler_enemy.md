---
title: Small Tentacler Enemy
category: entities
---

# Small Tentacler Enemy

This document details the configuration for the "Small Tentacler" enemy entity in Noita, focusing on its AI, combat, and physical attributes for modding purposes.

## Core Entity Configuration

The Small Tentacler is a flying enemy with ranged attack capabilities.

```xml
<Entity name="$animal_tentacler_small">
  <Base file="data/entities/base_enemy_flying.xml">
    <!-- ... other components ... -->
  </Base>
  <!-- ... other components ... -->
</Entity>
```

## Key Components and Attributes

### AnimalAIComponent

Controls the enemy's behavior, including its attack patterns and movement.

| Attribute                 | Description                                                              | Value                 |
| :------------------------ | :----------------------------------------------------------------------- | :-------------------- |
| `attack_ranged_entity_file` | File path for the projectile used in ranged attacks.                     | `data/entities/projectiles/freeze_circle.xml` |
| `attack_ranged_enabled`   | Enables or disables ranged attacks.                                      | `1` (Enabled)         |
| `attack_ranged_frames_between` | Minimum frames between consecutive ranged attacks.                       | `100`                 |
| `attack_ranged_offset_y`  | Vertical offset for the ranged attack origin.                            | `-8`                  |
| `attack_ranged_max_distance` | Maximum distance at which ranged attacks can be initiated.               | `38`                  |
| `can_fly`                 | Indicates if the entity can fly.                                         | `1` (Enabled)         |

### DamageModelComponent

Defines the entity's health and how it reacts to damage.

| Attribute               | Description                                                              | Value                 |
| :---------------------- | :----------------------------------------------------------------------- | :-------------------- |
| `hp`                    | Hit points of the entity.                                                | `0.75`                |
| `ragdoll_material`      | Material used for the ragdoll effect upon death.                         | `meat_slime`          |
| `blood_material`        | Material of the blood particles.                                         | `blood_fungi`         |
| `blood_sprite_directional` | File path for directional blood splatter particles.                      | `data/particles/bloodsplatters/bloodsplatter_directional_purple_$[1-3].xml` |
| `damage_multipliers`    | Modifiers for damage taken from specific sources.                        |                       |
| `freeze`                | Damage multiplier against freeze effects.                                | `0.4`                 |

### SpriteComponent

Determines the visual appearance of the entity.

| Attribute   | Description                               | Value                               |
| :---------- | :---------------------------------------- | :---------------------------------- |
| `image_file` | Path to the sprite's image definition file. | `data/enemies_gfx/tentacler_small.xml` |

### HitboxComponent

Defines the collision boundaries of the entity.

| Attribute     | Description                               | Value   |
| :------------ | :---------------------------------------- | :------ |
| `aabb_min_x`  | Minimum X-coordinate of the bounding box. | `-6.0`  |
| `aabb_max_x`  | Maximum X-coordinate of the bounding box. | `6.0`   |
| `aabb_min_y`  | Minimum Y-coordinate of the bounding box. | `-14`   |
| `aabb_max_y`  | Maximum Y-coordinate of the bounding box. | `1`     |
| `is_enemy`    | Indicates if the hitbox belongs to an enemy. | `1`     |

### CharacterPlatformingComponent

Governs the entity's movement physics, particularly for flying.

| Attribute         | Description                               | Value |
| :---------------- | :---------------------------------------- | :---- |
| `fly_speed_max_up` | Maximum upward flying speed.              | `40`  |
| `fly_speed_max_down` | Maximum downward flying speed.            | `40`  |
| `fly_speed_mult` | Multiplier for general flying speed.      | `5`   |
| `fly_velocity_x` | Base horizontal velocity when flying.     | `20`  |

### LightComponent

Adds a light source originating from the entity.

| Attribute | Description                               | Value |
| :-------- | :---------------------------------------- | :---- |
| `radius`  | The radius of the light.                  | `30`  |
| `r`, `g`, `b` | RGB color values for the light.           | `189`, `45`, `209` |

### AudioComponent & AudioLoopComponent

Manage the sound effects associated with the entity.

| Component           | Attribute     | Description                                     | Value                                     |
| :------------------ | :------------ | :---------------------------------------------- | :---------------------------------------- |
| `AudioComponent`    | `file`        | Path to the audio bank.                         | `data/audio/Desktop/animals.bank`         |
|                     | `event_root`  | Root event name for general sounds.             | `animals/slime`                           |
| `AudioLoopComponent`| `file`        | Path to the audio bank for looping sounds.      | `data/audio/Desktop/animals.bank`         |
|                     | `event_name`  | Name of the looping movement sound event.       | `animals/slimy_small/movement_loop`       |
|                     | `auto_play`   | Automatically starts the loop on entity spawn.  | `1` (Enabled)                             |