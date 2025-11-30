---
title: Wall Piece Projectile
category: entities
---

# Wall Piece Projectile

This document describes the configuration for the "Wall Piece" projectile entity in Noita, primarily focusing on its behavior and visual effects when used as a projectile.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
   >
  ...
</Entity>
```

*   **`name`**: Set to `$projectile_default`, indicating it uses a default projectile naming convention.
*   **`tags`**: Includes `projectile_player`, signifying it originates from player actions.

## Base Projectile Configuration

The `<Base>` tag inherits properties from `base_projectile.xml`.

```xml
<Base file="data/entities/base_projectile.xml" >
  <VelocityComponent
    gravity_y="0"
    mass="0.04"
  >
  </VelocityComponent>
</Base>
```

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `mass="0.04"`: Defines the projectile's mass.

## Projectile Component

This component dictates the projectile's core mechanics and interactions.

```xml
<ProjectileComponent 
  _enabled="1" 
  lob_min="0.8"
  lob_max="1.0"
  speed_min="0"
  speed_max="0"
  direction_random_rad="0"
  on_death_explode="0"
  on_death_gfx_leave_sprite="0" 
  on_lifetime_out_explode="0"
  explosion_dont_damage_shooter="1" 
  on_collision_die="1"
  die_on_liquid_collision="0"
  velocity_sets_scale="1"
  lifetime="400"
  damage="1.29"
  ragdoll_force_multiplier="0.0"
  ragdoll_fx_on_collision="BLOOD_SPRAY"
  hit_particle_force_multiplier="0.0"
  camera_shake_when_shot="0.0"
  bounces_left="0"
  muzzle_flash_file=""
  shoot_light_flash_radius="1"
  knockback_force="0"
  physics_impulse_coeff="0"
  ground_penetration_coeff="1"
  collide_with_shooter_frames="2"
  friendly_fire="1"
  >
  <config_explosion />
</ProjectileComponent>
```

**Key Attributes:**

*   **`lob_min`, `lob_max`**: Controls the minimum and maximum lob angle, set to `0.8` and `1.0` respectively.
*   **`speed_min`, `speed_max`**: Set to `0`, indicating the projectile does not have an initial speed.
*   **`direction_random_rad`**: Set to `0`, meaning the projectile travels in a fixed direction.
*   **`on_collision_die="1"`**: The projectile dies upon colliding with something.
*   **`lifetime="400"`**: The projectile exists for 400 frames.
*   **`damage="1.29"`**: The projectile deals 1.29 damage.
*   **`ragdoll_fx_on_collision="BLOOD_SPRAY"`**: Triggers a blood spray effect on collision.
*   **`friendly_fire="1"`**: The projectile can damage the shooter.
*   **`collide_with_shooter_frames="2"`**: The projectile will collide with the shooter for 2 frames after being fired.

## Light Component

This component adds a light source to the projectile.

```xml
<LightComponent 
  _enabled="1" 
  radius="20" 
  r="30"
  g="90"
  b="30">
</LightComponent>
```

*   **`radius="20"`**: The light has a radius of 20 units.
*   **`r="30"`, `g="90"`, `b="30"`**: Defines the light color as a greenish hue.

## Particle Emitter Component

This component emits particles to enhance the visual effect of the projectile.

```xml
<ParticleEmitterComponent 
  emitted_material_name="plasma_fading_green"
  offset.x="0"
  offset.y="0"
  gravity.y="0.0"
  x_vel_min="0"
  x_vel_max="0"
  y_vel_min="-2"
  y_vel_max="2"
  count_min="1"
  count_max="1"
  lifetime_min="0.05"
  lifetime_max="0.1"
  emit_real_particles="0"
  render_on_grid="1"
  emit_cosmetic_particles="1"
  emission_interval_min_frames="1"
  emission_interval_max_frames="2"
  area_circle_radius.max="4"
  is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name="plasma_fading_green"`**: Specifies the material of the emitted particles.
*   **`gravity.y="0.0"`**: Emitted particles are not affected by gravity.
*   **`y_vel_min="-2"`, `y_vel_max="2"`**: Particles have a slight vertical velocity.
*   **`lifetime_min="0.05"`, `lifetime_max="0.1"`**: Particles have a very short lifespan.
*   **`emit_cosmetic_particles="1"`**: Emits cosmetic particles for visual flair.
*   **`area_circle_radius.max="4"`**: Particles are emitted within a small circular area.