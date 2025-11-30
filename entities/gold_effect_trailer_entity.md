---
title: Gold Effect Trailer Entity
category: entities
---

# Gold Effect Trailer Entity

This entity defines a visual effect used in Noita trailers, primarily for creating a "gold" or "spark" appearance. It utilizes particle emitters and a homing component to achieve its visual behavior.

## Key Components

### ParticleEmitterComponent (Yellow Sparks)

This component is responsible for emitting yellow sparks.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark_yellow` - Specifies the material of the emitted particles.           |
| `gravity.y`               | `0.0` - No vertical gravity applied to the sparks.                          |
| `lifetime_min`            | `5.5` - Minimum lifetime of emitted sparks in seconds.                      |
| `lifetime_max`            | `25.5` - Maximum lifetime of emitted sparks in seconds.                     |
| `count_min`               | `10` - Minimum number of sparks emitted per emission.                       |
| `count_max`               | `20` - Maximum number of sparks emitted per emission.                       |
| `render_on_grid`          | `1` - Particles are rendered on the game grid.                              |
| `fade_based_on_lifetime`  | `1` - Particles fade out as their lifetime decreases.                       |
| `area_circle_radius.max`  | `256` - Maximum radius of the circular emission area.                       |
| `airflow_force`           | `0.5` - Force applied by airflow.                                           |
| `airflow_time`            | `0.01` - Duration airflow affects particles.                                |
| `airflow_scale`           | `0.05` - Scale of the airflow effect.                                       |
| `attractor_force`         | `2` - Force pulling particles towards an attractor.                         |
| `emission_interval_min_frames` | `1` - Minimum frames between emissions.                                     |
| `emission_interval_max_frames` | `1` - Maximum frames between emissions.                                     |
| `emit_cosmetic_particles` | `1` - Emits cosmetic particles.                                             |
| `is_emitting`             | `1` - The emitter is active.                                                |

### ParticleEmitterComponent (Gold Particles)

This component emits particles representing gold.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `gold` - Specifies the material of the emitted particles.                   |
| `gravity.y`               | `0.0` - No vertical gravity applied to the gold particles.                  |
| `lifetime_min`            | `15.5` - Minimum lifetime of gold particles in seconds.                     |
| `lifetime_max`            | `25.5` - Maximum lifetime of gold particles in seconds.                     |
| `count_min`               | `1` - Minimum number of gold particles emitted per emission.                |
| `count_max`               | `3` - Maximum number of gold particles emitted per emission.                |
| `render_on_grid`          | `1` - Particles are rendered on the game grid.                              |
| `fade_based_on_lifetime`  | `1` - Particles fade out as their lifetime decreases.                       |
| `area_circle_radius.max`  | `32` - Maximum radius of the circular emission area.                        |
| `airflow_force`           | `0.5` - Force applied by airflow.                                           |
| `airflow_time`            | `0.01` - Duration airflow affects particles.                                |
| `airflow_scale`           | `0.05` - Scale of the airflow effect.                                       |
| `attractor_force`         | `2` - Force pulling particles towards an attractor.                         |
| `emission_interval_min_frames` | `1` - Minimum frames between emissions.                                     |
| `emission_interval_max_frames` | `1` - Maximum frames between emissions.                                     |
| `emit_cosmetic_particles` | `1` - Emits cosmetic particles.                                             |

### VelocityComponent

Defines the basic physics properties of the entity.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `gravity_y` | `0` - No gravity applied to the entity. |
| `mass`    | `0.1` - The mass of the entity.           |

### HomingComponent

Allows the entity to home in on a target.

| Attribute              | Description                                                                 |
| :--------------------- | :-------------------------------------------------------------------------- |
| `target_tag`           | `prey` - The tag of the entity to target.                                   |
| `homing_targeting_coeff` | `30` - Coefficient determining how strongly it targets.                     |
| `detect_distance`      | `800` - The distance at which the entity can detect its target.             |
| `homing_velocity_multiplier` | `0.9` - Multiplier for the entity's velocity when homing.                 |

### ProjectileComponent

Configures the entity as a projectile, though with minimal projectile-like behavior for this effect.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `speed_min`               | `80` - Minimum projectile speed.                                            |
| `speed_max`               | `80` - Maximum projectile speed.                                            |
| `friction`                | `0` - No friction applied.                                                  |
| `direction_random_rad`    | `0` - No random direction applied.                                          |
| `on_death_explode`        | `0` - Does not explode on death.                                            |
| `on_death_gfx_leave_sprite` | `0` - Does not leave a sprite on death.                                     |
| `on_lifetime_out_explode` | `0` - Does not explode when lifetime ends.                                  |
| `explosion_dont_damage_shooter` | `1` - Does not damage the shooter if it explodes (though it doesn't).     |
| `on_collision_die`        | `0` - Does not die on collision.                                            |
| `lifetime`                | `120` - The lifetime of the projectile in seconds.                          |
| `damage`                  | `0` - Deals no damage.                                                      |
| `velocity_sets_scale`     | `0` - Velocity does not affect scale.                                       |
| `ragdoll_force_multiplier`| `0` - No ragdoll force applied.                                             |
| `hit_particle_force_multiplier` | `0` - No particle force applied on hit.                                     |
| `camera_shake_when_shot`  | `0` - No camera shake when shot.                                            |
| `bounces_left`            | `0` - Does not bounce.                                                      |
| `muzzle_flash_file`       | `""` - No muzzle flash.                                                     |
| `shoot_light_flash_radius`| `1` - Radius of light flash when shot.                                      |
| `knockback_force`         | `0` - No knockback force.                                                   |

#### `config_explosion` (within ProjectileComponent)

This sub-component defines explosion properties, but they are all disabled for this entity.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `never_cache`             | `1` - The explosion configuration is never cached.                          |
| `camera_shake`            | `0` - No camera shake from explosion.                                       |
| `explosion_radius`        | `0` - No explosion radius.                                                  |
| `explosion_sprite`        | `""` - No explosion sprite.                                                 |
| `explosion_sprite_lifetime` | `0` - No lifetime for explosion sprite.                                     |
| `create_cell_probability` | `0` - No cell creation probability.                                         |
| `hole_destroy_liquid`     | `0` - Does not destroy liquid.                                              |
| `explosion_sprite_emissive` | `0` - Explosion sprite is not emissive.                                     |
| `explosion_sprite_additive` | `0` - Explosion sprite is not additive.                                     |
| `hole_enabled`            | `0` - Holes are not enabled.                                                |
| `ray_energy`              | `0` - No ray energy.                                                        |
| `damage`                  | `0` - No damage from explosion.                                             |
| `particle_effect`         | `0` - No particle effect from explosion.                                    |
| `damage_mortals`          | `0` - Does not damage mortals.                                              |
| `physics_explosion_power.min` | `0` - Minimum physics explosion power.                                      |
| `physics_explosion_power.max` | `0` - Maximum physics explosion power.                                      |
| `physics_throw_enabled`   | `0` - Physics throw is not enabled.                                         |
| `shake_vegetation`        | `0` - Does not shake vegetation.                                            |
| `sparks_enabled`          | `0` - Sparks are not enabled.                                               |
| `stains_enabled`          | `0` - Stains are not enabled.                                               |

### LuaComponent

Attaches a Lua script to the entity.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `execute_on_removed`  | `1` - The script executes when the entity is removed.                       |
| `execute_every_n_frame` | `-1` - Script executes only once (when removed).                            |
| `script_source_file`  | `data/scripts/trailer/midas_end.lua` - Path to the Lua script.              |
| `remove_after_executed` | `0` - The entity is not removed after the script executes.                |