---
title: Infestation Projectile
category: entities
---

# Infestation Projectile

This document details the configuration of the "Infestation" projectile entity in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The projectile is defined by the `<Entity>` tag, with the primary name `$projectile_default` and tagged as `projectile_player`.

```xml
<Entity
  name="$projectile_default" tags="projectile_player"
>
```

## Base Projectile Properties

Inherits fundamental projectile behavior from `base_projectile.xml`.

### Velocity Component

Controls the projectile's movement characteristics.

```xml
<Base file="data/entities/base_projectile.xml">
  <VelocityComponent
    gravity_y="0"
    air_friction="0.6"
    mass="0.03"
  >
  </VelocityComponent>
</Base>
```

*   `gravity_y="0"`: No vertical gravity applied.
*   `air_friction="0.6"`: Moderate air resistance.
*   `mass="0.03"`: Low mass.

## Projectile Component - Key Attributes

This component defines the specific behaviors and effects of the Infestation projectile.

```xml
<ProjectileComponent
  _enabled="1"
  lob_min="0.5"
  lob_max="0.7"
  speed_min="350"
  speed_max="750"
  friction="1"
  direction_random_rad="6.283185307"
  on_death_explode="0"
  on_death_gfx_leave_sprite="0"
  on_lifetime_out_explode="0"
  explosion_dont_damage_shooter="1"
  on_collision_die="1"
  on_collision_remove_projectile="0"
  lifetime="600"
  damage="0.05"
  damage_scaled_by_speed="1"
  lifetime_randomness="7"
  ragdoll_force_multiplier="0"
  hit_particle_force_multiplier="0.1"
  create_shell_casing="0"
  muzzle_flash_file=""
  shoot_light_flash_radius="20"
  die_on_low_velocity="1"
  die_on_low_velocity_limit="5"
  bounce_always="1"
  bounces_left="20"
  bounce_energy="1.0"
  velocity_sets_rotation="1"
  velocity_updates_animation="1"
  velocity_sets_scale="1"
  velocity_sets_scale_coeff="0.6"
  knockback_force="0.4"
  physics_impulse_coeff="1200"
  collide_with_shooter_frames="120"
  friendly_fire="1"
  damage_every_x_frames="20"
>
  <damage_by_type
    slice="0"
  >
  </damage_by_type>
  <config_explosion>
  </config_explosion>
</ProjectileComponent>
```

*   `lob_min`/`lob_max`: Controls the arc of the projectile.
*   `speed_min`/`speed_max`: Defines the projectile's speed range.
*   `lifetime`: Duration in frames before the projectile is removed.
*   `damage`: Base damage dealt.
*   `damage_scaled_by_speed`: Damage increases with projectile velocity.
*   `bounce_always="1"`: The projectile will always bounce.
*   `bounces_left="20"`: Maximum number of bounces.
*   `knockback_force="0.4"`: The force applied to knock back entities on hit.
*   `damage_every_x_frames="20"`: Damage is applied every 20 frames.

## Audio Component

Defines the sound played when the projectile is active.

```xml
<AudioComponent
  file="data/audio/Desktop/projectiles.bank"
  event_root="player_projectiles/bullet_burst_of_air">
</AudioComponent>
```

*   `file`: Path to the audio bank.
*   `event_root`: The specific sound event to trigger.

## Particle Emitter Component

Generates visual particles associated with the projectile.

```xml
<ParticleEmitterComponent
  emitted_material_name="spark_purple_bright"
  gravity.y="0"
  x_vel_min="-3"
  x_vel_max="3"
  y_vel_min="-3"
  y_vel_max="3"
  count_min="1"
  count_max="1"
  lifetime_min="0.2"
  lifetime_max="0.5"
  is_trail="1"
  emit_cosmetic_particles="1"
  is_emitting="1"
>
</ParticleEmitterComponent>
```

*   `emitted_material_name`: The material used for the particles (e.g., "spark\_purple\_bright").
*   `is_trail="1"`: The particles form a trail.
*   `emit_cosmetic_particles="1"`: Particles are purely cosmetic.

## Area Damage Component

Applies damage to entities within a specified radius over time.

```xml
<AreaDamageComponent
  aabb_min.x="-6"
  aabb_min.y="-6"
  aabb_max.x="6"
  aabb_max.y="6"
  damage_per_frame="0.05"
  update_every_n_frame="1"
  entities_with_tag="homing_target"
  damage_type="DAMAGE_PROJECTILE"
>
</AreaDamageComponent>
```

*   `aabb_min`/`aabb_max`: Defines the bounding box for area damage.
*   `damage_per_frame`: The amount of damage dealt per frame within the area.
*   `entities_with_tag="homing_target"`: Only applies damage to entities with the "homing\_target" tag.

## Variable Storage Component

Stores a variable related to the projectile's own file path.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/deck/infestation.xml"
>
</VariableStorageComponent>
```