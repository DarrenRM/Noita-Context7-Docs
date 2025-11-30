---
title: Spitter Tier 2 Projectile
category: entities
---

# Spitter Tier 2 Projectile

This document details the configuration for the "Spitter Tier 2" projectile in Noita, designed for AI-assisted modding.

## Entity Definition

The core of the projectile is defined by an `<Entity>` tag.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
  <!-- ... components ... -->
</Entity>
```

-   `name="$projectile_default"`: A placeholder name, often overridden by specific projectile types.
-   `tags="projectile_player"`: Identifies this entity as a projectile fired by the player.

## Base Projectile Configuration

Inherits fundamental projectile properties from `base_projectile.xml`.

```xml
<Base file="data/entities/base_projectile.xml" >
  <VelocityComponent
    gravity_y="200"
    air_friction="2.7"
    mass="0.02"
    >
  </VelocityComponent>
</Base>
```

-   `gravity_y="200"`: Controls the downward acceleration due to gravity.
-   `air_friction="2.7"`: Affects how quickly the projectile loses velocity in the air.
-   `mass="0.02"`: The projectile's mass, influencing its interaction with physics.

## Projectile Component - Key Attributes

This component defines the unique behaviors and properties of the Spitter Tier 2 projectile.

```xml
<ProjectileComponent
  _enabled="1"
  lob_min="0.5"
  lob_max="0.7"
  speed_min="600"
  speed_max="800"
  friction="1"
  direction_random_rad="0.00"
  on_death_explode="1"
  on_lifetime_out_explode="1"
  explosion_dont_damage_shooter="1"
  on_collision_die="1"
  lifetime="30"
  damage="0.5"
  bounce_always="1"
  bounces_left="10"
  bounce_energy="0.6"
  bounce_fx_file="data/entities/particles/bounce_effects/spitter_green.xml"
  velocity_sets_scale="1"
  lifetime_randomness="12"
  ragdoll_force_multiplier="0.05"
  hit_particle_force_multiplier="0.3"
  velocity_sets_rotation="1"
  muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_magic_small.xml"
  shoot_light_flash_radius="80"
  shoot_light_flash_r="125"
  shoot_light_flash_g="245"
  shoot_light_flash_b="50"
  knockback_force="1.0"
  physics_impulse_coeff="2500"
  >
  <!-- config_explosion -->
</ProjectileComponent>
```

### Key Attributes:

-   `lob_min`, `lob_max`: Controls the arc of the projectile.
-   `speed_min`, `speed_max`: Defines the initial velocity range.
-   `on_death_explode="1"`: Causes an explosion when the projectile dies (e.g., on collision or lifetime out).
-   `on_lifetime_out_explode="1"`: Triggers an explosion when the projectile's lifetime expires.
-   `on_collision_die="1"`: The projectile is destroyed upon colliding with something.
-   `damage="0.5"`: The base damage dealt by the projectile.
-   `bounce_always="1"`: The projectile will always attempt to bounce.
-   `bounces_left="10"`: Maximum number of bounces allowed.
-   `bounce_energy="0.6"`: The proportion of energy retained after each bounce.
-   `bounce_fx_file`: Specifies the particle effect to spawn on bounce.
-   `lifetime="30"`: The maximum duration in frames before the projectile is destroyed.
-   `lifetime_randomness="12"`: Adds variation to the projectile's lifetime.
-   `knockback_force="1.0"`: The force applied to entities hit by the projectile.

### `config_explosion` (Nested within `ProjectileComponent`)

Defines the properties of the explosion that occurs when `on_death_explode` or `on_lifetime_out_explode` is triggered.

```xml
<config_explosion
  never_cache="1"
  damage="0.0"
  camera_shake="0"
  explosion_radius="2"
  ray_energy="400000"
  damage_mortals="1"
  shake_vegetation="1"
  material_sparks_enabled="1"
  material_sparks_count_max="2"
  stains_enabled="1"
  stains_radius="3" >
</config_explosion>
```

-   `damage="0.0"`: The explosion itself deals no direct damage (damage is handled by the projectile's `damage` attribute).
-   `explosion_radius="2"`: The area of effect for the explosion.
-   `ray_energy="400000"`: The energy value for destructive rays cast by the explosion.
-   `damage_mortals="1"`: The explosion can damage living entities.
-   `stains_enabled="1"`: Creates stains on surfaces where the explosion occurs.
-   `stains_radius="3"`: The radius of the stains.

## Sprite Component

Defines the visual appearance of the projectile.

```xml
<SpriteComponent
  _enabled="1"
  alpha="1"
  image_file="data/projectiles_gfx/spitter_green.xml"
  rect_animation="fireball"
  emissive="1"
  additive="1"
  >
</SpriteComponent>
```

-   `image_file`: Path to the sprite sheet or texture atlas.
-   `rect_animation="fireball"`: Specifies the animation to use from the `image_file`.
-   `emissive="1"`, `additive="1"`: These flags contribute to a glowing or bright appearance.

## Audio Component

Handles sound effects associated with the projectile.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/bullet_smg">
</AudioComponent>
```

-   `file`: Path to the audio bank.
-   `event_root`: The base event name for sounds related to this projectile.

## Light Component

Adds a light source to the projectile.

```xml
<LightComponent
  _enabled="1"
  radius="60"
  fade_out_time="0.1"
  r="40"
  g="80"
  b="10">
</LightComponent>
```

-   `radius`: The range of the light.
-   `r`, `g`, `b`: The color components of the light.

## Particle Emitter Components

These components spawn particles to enhance visual effects.

### Particle Emitter 1 (Sparks)

```xml
<ParticleEmitterComponent
  emitted_material_name="spark_green"
  offset.x="0"
  offset.y="0"
  x_pos_offset_min="-1"
  y_pos_offset_min="-1"
  x_pos_offset_max="1"
  y_pos_offset_max="1"
  x_vel_min="-20"
  x_vel_max="20"
  y_vel_min="-20"
  y_vel_max="20"
  count_min="1"
  count_max="6"
  lifetime_min="0.6"
  lifetime_max="1.1"
  create_real_particles="0"
  emit_cosmetic_particles="1"
  render_on_grid="1"
  gravity.y="20"
  fade_based_on_lifetime="1"
  emission_interval_min_frames="1"
  emission_interval_max_frames="1"
  is_emitting="1" >
</ParticleEmitterComponent>
```

-   `emitted_material_name="spark_green"`: Specifies the type of particle to emit.
-   `count_min`, `count_max`: Number of particles emitted per interval.
-   `lifetime_min`, `lifetime_max`: Duration of each particle.
-   `gravity.y="20"`: Particles are affected by gravity.

### Particle Emitter 2 (Secondary Sparks)

```xml
<ParticleEmitterComponent
  emitted_material_name="spark_green"
  offset.x="0"
  offset.y="0"
  count_min="1"
  count_max="8"
  gravity.y="-10"
  lifetime_min="0.25"
  lifetime_max="0.5"
  airflow_force="1.2"
  airflow_time="0.1"
  airflow_scale="0.03"
  render_on_grid="1"
  fade_based_on_lifetime="1"
  create_real_particles="0"
  emit_cosmetic_particles="1"
  emission_interval_min_frames="1"
  emission_interval_max_frames="1"
  x_pos_offset_min="-1"
  y_pos_offset_min="-1"
  x_pos_offset_max="1"
  y_pos_offset_max="1"
  is_emitting="1" >
</ParticleEmitterComponent>
```

-   `gravity.y="-10"`: These particles are affected by upward gravity (or a downward force if gravity is positive).
-   `airflow_force`, `airflow_time`, `airflow_scale`: These parameters influence how particles react to air currents.

## Variable Storage Component

Stores variables, often used to reference the entity's own file path.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/deck/spitter_tier_2.xml"
  >
</VariableStorageComponent>
```

-   `name="projectile_file"`: The name of the variable.
-   `value_string`: The value assigned to the variable, in this case, the path to this entity's XML file.