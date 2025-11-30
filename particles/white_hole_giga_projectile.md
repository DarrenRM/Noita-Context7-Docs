---
title: White Hole Giga Projectile
category: data/entities
---

# White Hole Giga Projectile

This document details the configuration of the "White Hole Giga" projectile in Noita, focusing on its attributes relevant to AI-assisted modding.

## Core Functionality

The White Hole Giga is a powerful player projectile that creates a localized gravitational anomaly, pulling in and damaging nearby entities.

## Key Components and Attributes

### ProjectileComponent

This component defines the fundamental behavior of the projectile.

| Attribute                 | Value      | Description                                                                                                |
| :------------------------ | :--------- | :--------------------------------------------------------------------------------------------------------- |
| `lob_min`, `lob_max`      | `0.8`, `1.0` | Controls the projectile's lobbing behavior.                                                                |
| `speed_min`, `speed_max`  | `100`, `140` | Defines the projectile's initial speed range.                                                              |
| `on_death_explode`        | `1`        | The projectile explodes upon death.                                                                        |
| `on_lifetime_out_explode` | `1`        | The projectile explodes when its lifetime expires.                                                         |
| `explosion_dont_damage_shooter` | `1`    | The explosion does not damage the entity that shot the projectile.                                           |
| `lifetime`                | `1000`     | The duration the projectile exists before expiring.                                                        |
| `damage`                  | `0`        | Base damage of the projectile itself (the area damage component handles the main damage).                  |
| `damage_every_x_frames`   | `5`        | How often the projectile deals damage (in frames).                                                         |
| `knockback_force`         | `0.1`      | The force applied to entities when hit by the projectile.                                                  |
| `penetrate_entities`      | `1`        | Allows the projectile to pass through multiple entities.                                                   |
| `camera_shake_when_shot`  | `0.4`      | The intensity of camera shake when the projectile is fired.                                                |
| `collide_with_shooter_frames` | `10`   | The number of frames the projectile will ignore collisions with its shooter.                               |
| `friendly_fire`           | `1`        | The projectile can damage friendly entities.                                                               |
| `shoot_light_flash_radius` | `250`     | The radius of the light flash emitted when the projectile is shot.                                         |
| `shoot_light_flash_r`, `g`, `b` | `255`, `180`, `230` | The RGB color of the light flash.                                                                          |

#### `config_explosion`

Nested within `ProjectileComponent`, this defines the explosion properties.

| Attribute              | Value                                     | Description                                                                                              |
| :--------------------- | :---------------------------------------- | :------------------------------------------------------------------------------------------------------- |
| `damage`               | `0`                                       | Damage dealt by the explosion itself (area damage component handles the main damage).                    |
| `camera_shake`         | `0`                                       | Camera shake intensity of the explosion.                                                                 |
| `explosion_radius`     | `1`                                       | The radius of the visual explosion effect.                                                               |
| `explosion_sprite`     | `data/particles/black_hole_big_circle_out.xml` | The sprite used for the explosion effect.                                                                |
| `explosion_sprite_emissive` | `1`                                   | Makes the explosion sprite emissive (glows).                                                             |
| `explosion_sprite_additive` | `1`                                   | Makes the explosion sprite additive (blends with background).                                            |
| `hole_enabled`         | `1`                                       | Enables the "hole" effect of the explosion, likely referring to the black hole visual.                   |
| `damage_mortals`       | `1`                                       | The explosion deals damage to mortal entities.                                                           |
| `physics_throw_enabled`| `0`                                       | Disables physics-based throwing of debris from the explosion.                                            |
| `sparks_count_min`, `max` | `4`, `1`                                | The range for the number of sparks generated by the explosion.                                           |
| `spark_material`       | `spark_white`                             | The material used for the sparks.                                                                        |

### SpriteComponent

Defines the visual representation of the projectile.

| Attribute      | Value                               | Description                                                                                              |
| :------------- | :---------------------------------- | :------------------------------------------------------------------------------------------------------- |
| `offset_x`, `y`| `80`, `80`                          | Offset of the sprite from the projectile's origin.                                                       |
| `emissive`     | `1`                                 | Makes the sprite emissive.                                                                               |
| `z_index`      | `-1`                                | Controls the rendering layer of the sprite.                                                              |
| `image_file`   | `data/projectiles_gfx/white_hole_giga.png` | The texture file for the projectile's sprite.                                                            |

### MagicConvertMaterialComponent

This component allows the projectile to convert materials in its vicinity.

| Attribute     | Value | Description                                                                                                |
| :------------ | :---- | :--------------------------------------------------------------------------------------------------------- |
| `extinguish_fire` | `1`   | The projectile can extinguish fire.                                                                        |
| `is_circle`   | `1`   | The conversion effect is circular.                                                                         |
| `radius`      | `120` | The radius of the material conversion effect.                                                              |
| `loop`        | `1`   | The conversion effect loops.                                                                               |

### CellEaterComponent

This component allows the projectile to consume certain materials.

| Attribute       | Value                               | Description                                                                                                |
| :-------------- | :---------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `radius`        | `60`                                | The radius within which the component eats cells.                                                          |
| `eat_probability` | `80`                                | The probability (in percent) of eating a cell.                                                             |
| `ignored_material`| `gem_box2d_yellow_sun`              | A material that this component will not eat.                                                               |

### AreaDamageComponent

This component deals damage to entities within a specified area.

| Attribute        | Value              | Description                                                                                                |
| :--------------- | :----------------- | :--------------------------------------------------------------------------------------------------------- |
| `aabb_min.x`, `y`| `-72`, `-72`       | The minimum X and Y coordinates of the damage area's bounding box.                                         |
| `aabb_max.x`, `y`| `72`, `72`         | The maximum X and Y coordinates of the damage area's bounding box.                                         |
| `damage_per_frame`| `0.14`             | The amount of damage dealt per frame to entities within the area.                                          |
| `update_every_n_frame`| `1`            | How often the damage is applied (in frames).                                                               |
| `entities_with_tag`| `mortal`           | Only applies damage to entities with the "mortal" tag.                                                     |
| `death_cause`    | `$action_white_hole_giga` | The cause of death recorded when an entity is killed by this damage.                                       |
| `damage_type`    | `DAMAGE_HOLY`      | The type of damage dealt.                                                                                  |

### ParticleEmitterComponent (x2)

These components are responsible for emitting particles, creating visual effects. Both emitters are configured identically.

| Attribute                   | Value   | Description                                                                                                |
| :-------------------------- | :------ | :--------------------------------------------------------------------------------------------------------- |
| `emitted_material_name`     | `spark_white` | The material of the particles being emitted.                                                               |
| `fade_based_on_lifetime`    | `1`     | Particles fade out as their lifetime decreases.                                                            |
| `x_vel_min`, `max`, `y_vel_min`, `max` | `-80` to `80` | The velocity range of emitted particles.                                                                   |
| `area_circle_radius.min`, `max` | `24`, `72` | The radius range of the emission area.                                                                     |
| `velocity_always_away_from_center` | `300` | Particles are always pushed away from the center of the emission.                                          |
| `gravity.y`                 | `0`     | No gravity applied to the emitted particles.                                                               |
| `friction`                  | `0.1`   | Friction applied to the emitted particles.                                                                 |
| `airflow_force`, `time`, `scale` | `0.9`, `0.101`, `0.81` | Parameters controlling airflow effects on particles.                                                       |
| `count_min`, `max`          | `40`, `60` | The number of particles emitted per emission cycle.                                                        |
| `lifetime_min`, `max`       | `0.1`, `1.4` | The lifetime range of emitted particles.                                                                   |
| `create_real_particles`     | `0`     | Does not create actual physics-simulated particles.                                                        |
| `emit_cosmetic_particles`   | `1`     | Emits particles primarily for visual effect.                                                               |
| `draw_as_long`              | `1`     | Particles are drawn as trails.                                                                             |
| `collide_with_grid`         | `0`     | Particles do not collide with the game grid.                                                               |
| `render_on_grid`            | `1`     | Particles are rendered even when the camera is not directly over them.                                     |
| `emission_interval_min_frames`, `max_frames` | `1`, `1` | Particles are emitted every frame.                                                                         |
| `attractor_force`           | `16`    | A force that attracts particles towards a point.                                                           |
| `render_ultrabright`        | `1`     | Particles are rendered with ultrabrightness.                                                               |
| `is_emitting`               | `1`     | The particle emitter is active.                                                                            |

### BlackHoleComponent

This component simulates the black hole effect, attracting entities.

| Attribute           | Value | Description                                                                                                |
| :------------------ | :---- | :--------------------------------------------------------------------------------------------------------- |
| `particle_attractor_force` | `-8`  | The force that attracts particles towards the black hole. Negative values indicate attraction.             |
| `damage_probability`| `0.55`| The probability of dealing damage to entities within the black hole's radius.                              |
| `radius`            | `160` | The radius of the black hole's effect.                                                                     |

### AudioComponent and AudioLoopComponent

These components handle the sound effects associated with the projectile.

| Attribute     | Value                                 | Description                                                                                                |
| :------------ | :------------------------------------ | :--------------------------------------------------------------------------------------------------------- |
| `file`        | `data/audio/Desktop/projectiles.bank` | The audio bank file containing the sound events.                                                           |
| `event_root`  | `player_projectiles/black_hole_giga`  | The root event name for the projectile's sounds.                                                           |
| `event_name`  | `player_projectiles/black_hole_giga/loop` | The specific event name for the looping sound.                                                             |
| `auto_play`   | `1`                                   | The looping sound automatically plays when the projectile is active.                                       |

### LooseGroundComponent

This component allows the projectile to cause nearby ground to collapse.

| Attribute          | Value                                 | Description                                                                                                |
| :----------------- | :------------------------------------ | :--------------------------------------------------------------------------------------------------------- |
| `max_distance`     | `260`                                 | The maximum distance from the projectile at which ground can collapse.                                     |
| `probability`      | `0.5`                                 | The probability of ground collapse occurring.                                                              |
| `collapse_images`  | `data/procedural_gfx/collapse_huge/$[0-14].png` | The image files used for the ground collapse effect.                                                       |

### LuaComponent

This component executes a Lua script to further define the projectile's behavior.

| Attribute         | Value                                | Description                                                                                                |
| :---------------- | :----------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `script_source_file` | `data/scripts/projectiles/white_hole_gravity.lua` | The path to the Lua script file that controls additional functionality.                                    |
| `execute_every_n_frame` | `1`                              | The script executes every frame.                                                                           |