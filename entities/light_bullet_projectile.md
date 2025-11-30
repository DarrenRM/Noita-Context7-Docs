---
title: Light Bullet Projectile
category: entities
---

# Light Bullet Projectile

This document details the configuration for the "Light Bullet" projectile entity in Noita, intended for AI-assisted modding.

## Entity Definition

The core entity definition for the light bullet.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
  <!-- ... components ... -->
</Entity>
```

-   **`name`**: `$projectile_default` - A placeholder name, often overridden by specific projectile types.
-   **`tags`**: `projectile_player` - Identifies this entity as a projectile fired by the player.

## Base Projectile Configuration

Inherits fundamental projectile properties.

```xml
<Base file="data/entities/base_projectile.xml" >
  <VelocityComponent
    gravity_y="200"
    air_friction="1.7"
    mass="0.04"
  >
  </VelocityComponent>
</Base>
```

-   **`gravity_y`**: `200` - The strength of gravity affecting the projectile.
-   **`air_friction`**: `1.7` - Resistance from air, slowing the projectile.
-   **`mass`**: `0.04` - The projectile's mass, influencing its interaction with physics.

## Projectile Component - Key Attributes

This component defines the projectile's behavior and effects.

```xml
<ProjectileComponent
  _enabled="1"
  lob_min="0.5"
  lob_max="0.7"
  speed_min="750"
  speed_max="850"
  friction="1"
  direction_random_rad="0.00"
  on_death_explode="1"
  on_lifetime_out_explode="1"
  explosion_dont_damage_shooter="1"
  on_collision_die="1"
  lifetime="40"
  damage="0.12"
  velocity_sets_scale="1"
  lifetime_randomness="7"
  ragdoll_force_multiplier="0.005"
  hit_particle_force_multiplier="0.1"
  muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_small_pink.xml"
  shoot_light_flash_r="255"
  shoot_light_flash_g="160"
  shoot_light_flash_b="255"
  shoot_light_flash_radius="64"
  knockback_force="0"
>
  <!-- ... config_explosion ... -->
</ProjectileComponent>
```

-   **`lob_min` / `lob_max`**: `0.5` / `0.7` - Controls the arc of the projectile.
-   **`speed_min` / `speed_max`**: `750` / `850` - The projectile's initial velocity range.
-   **`on_death_explode`**: `1` - The projectile explodes when it dies.
-   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
-   **`on_collision_die`**: `1` - The projectile is destroyed upon collision.
-   **`lifetime`**: `40` - The base duration in frames before the projectile expires.
-   **`lifetime_randomness`**: `7` - Adds variability to the projectile's lifetime.
-   **`damage`**: `0.12` - The base damage dealt by the projectile.
-   **`muzzle_flash_file`**: `data/entities/particles/muzzle_flashes/muzzle_flash_small_pink.xml` - Specifies the muzzle flash particle effect.
-   **`shoot_light_flash_r/g/b/radius`**: `255`/`160`/`255`/`64` - Defines the color and radius of the light flash when fired.
-   **`knockback_force`**: `0` - No knockback is applied by this projectile.

### `config_explosion` - Explosion Properties

Details of the explosion that occurs on death or lifetime expiry.

```xml
<config_explosion
  damage="0.0"
  camera_shake="0.5"
  explosion_radius="2"
  explosion_sprite="data/particles/explosion_008_pink.xml"
  hole_enabled="1"
  ray_energy="400000"
  max_durability_to_destroy="8"
  physics_explosion_power.min="0.22"
  physics_explosion_power.max="0.3"
  physics_throw_enabled="1"
  shake_vegetation="1"
  material_sparks_enabled="1"
  stains_enabled="1"
  stains_radius="3"
>
</config_explosion>
```

-   **`damage`**: `0.0` - The explosion itself does not deal direct damage.
-   **`camera_shake`**: `0.5` - The intensity of camera shake caused by the explosion.
-   **`explosion_radius`**: `2` - The area of effect for the explosion.
-   **`explosion_sprite`**: `data/particles/explosion_008_pink.xml` - The visual effect of the explosion.
-   **`hole_enabled`**: `1` - The explosion can create holes in terrain.
-   **`ray_energy`**: `400000` - The energy of the destructive rays emitted by the explosion.
-   **`max_durability_to_destroy`**: `8` - The maximum durability of terrain that can be destroyed.
-   **`physics_explosion_power.min/max`**: `0.22` / `0.3` - The force of the physics-based explosion.
-   **`shake_vegetation`**: `1` - The explosion will affect vegetation.
-   **`material_sparks_enabled`**: `1` - Sparks will be generated from destroyed materials.
-   **`stains_enabled`**: `1` - Creates stains on surfaces.
-   **`stains_radius`**: `3` - The radius of the stains.

## Sprite Component

Defines the visual representation of the projectile.

```xml
<SpriteComponent
  _enabled="1"
  alpha="1"
  image_file="data/projectiles_gfx/spark.xml"
  additive="1"
>
</SpriteComponent>
```

-   **`image_file`**: `data/projectiles_gfx/spark.xml` - The sprite asset used for the projectile.
-   **`additive`**: `1` - The sprite uses additive blending for a glowing effect.

## Particle Emitters

These components generate cosmetic particles to enhance the visual effect.

### Dense Emitter

Generates a dense trail of particles.

```xml
<ParticleEmitterComponent
  emitted_material_name="plasma_fading_pink"
  count_min="1"
  count_max="4"
  lifetime_min="0.1"
  lifetime_max="0.2"
  is_trail="1"
  airflow_force="10.5"
  emission_interval_min_frames="1"
  emission_interval_max_frames="1"
  create_real_particles="0"
  is_emitting="1"
>
</ParticleEmitterComponent>
```

-   **`emitted_material_name`**: `plasma_fading_pink` - The material of the particles emitted.
-   **`is_trail`**: `1` - Indicates this emitter creates a particle trail.
-   **`create_real_particles`**: `0` - These are cosmetic particles, not physical entities.

### Sparse Emitter

Generates sparser particles with a slight velocity.

```xml
<ParticleEmitterComponent
  emitted_material_name="plasma_fading_pink"
  x_vel_min="20"
  x_vel_max="40"
  count_min="1"
  count_max="2"
  lifetime_min="0.6"
  lifetime_max="0.8"
  is_trail="0"
  airflow_force="1.5"
  emission_interval_max_frames="10"
  create_real_particles="0"
  is_emitting="1"
>
</ParticleEmitterComponent>
```

-   **`x_vel_min` / `x_vel_max`**: `20` / `40` - Particles have a horizontal velocity.
-   **`is_trail`**: `0` - This emitter does not create a continuous trail.

### Very Sparse Emitter

Generates very infrequent, longer-lasting particles.

```xml
<ParticleEmitterComponent
  emitted_material_name="plasma_fading_pink"
  x_vel_min="10"
  x_vel_max="20"
  count_min="1"
  count_max="1"
  lifetime_min="1.4"
  lifetime_max="1.5"
  is_trail="0"
  airflow_force="0.5"
  emission_interval_min_frames="10"
  emission_interval_max_frames="20"
  create_real_particles="0"
  is_emitting="1"
>
</ParticleEmitterComponent>
```

-   **`emission_interval_min_frames` / `max_frames`**: `10` / `20` - Particles are emitted infrequently.

## Light Component

Adds a light source to the projectile.

```xml
<LightComponent
  _enabled="1"
  r="255"
  g="40"
  b="255"
  radius="30"
>
</LightComponent>
```

-   **`r` / `g` / `b`**: `255` / `40` / `255` - The RGB color of the light (a purplish-pink).
-   **`radius`**: `30` - The radius of the light emitted.

## Audio Component

Defines the sound effects associated with the projectile.

```xml
<AudioComponent
  file="data/audio/Desktop/projectiles.bank"
  event_root="player_projectiles/bullet_light">
</AudioComponent>
```

-   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
-   **`event_root`**: `player_projectiles/bullet_light` - The specific sound event for this projectile.

## Variable Storage Component

Stores variables related to the projectile.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/deck/light_bullet.xml"
>
</VariableStorageComponent>
```

-   **`name`**: `projectile_file` - The name of the variable.
-   **`value_string`**: `data/entities/projectiles/deck/light_bullet.xml` - The value, pointing to the projectile's own XML file.