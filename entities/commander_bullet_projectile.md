---
title: Commander Bullet Projectile
category: entities
---

# Commander Bullet Projectile

This document details the configuration for the "Commander Bullet" projectile in Noita, intended for AI-assisted modding.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior and characteristics of the projectile.

```xml
<ProjectileComponent 
  _enabled="1" 
  lob_min="0.5"
  lob_max="0.7"
  speed_min="150"
  speed_max="150"
  friction="1"
  direction_random_rad="0.00"
  on_death_explode="1"
  on_death_gfx_leave_sprite="0" 
  on_lifetime_out_explode="1"
  explosion_dont_damage_shooter="1"
  on_collision_die="1"
  lifetime="300"
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
  penetrate_entities="1"
  >
  <!-- ... explosion config ... -->
</ProjectileComponent>
```

### Key Attributes:

*   **`lob_min`, `lob_max`**: Controls the arc of the projectile. Values between 0.5 and 0.7 suggest a moderate arc.
*   **`speed_min`, `speed_max`**: Sets the projectile's speed. Here, it's a fixed 150 units.
*   **`on_death_explode`**: If `1`, the projectile will explode upon death (e.g., collision or lifetime end).
*   **`on_lifetime_out_explode`**: If `1`, the projectile explodes when its `lifetime` expires.
*   **`on_collision_die`**: If `1`, the projectile is destroyed upon colliding with an entity.
*   **`lifetime`**: The duration in frames before the projectile expires. 300 frames is 5 seconds.
*   **`damage`**: The base damage dealt by the projectile. 0.12 is a low value.
*   **`penetrate_entities`**: If `1`, the projectile can pass through multiple entities.
*   **`muzzle_flash_file`**: Specifies the particle effect used for the muzzle flash.
*   **`shoot_light_flash_r/g/b/radius`**: Defines the color and radius of the light flash when the projectile is fired.

## Explosion Configuration

The `config_explosion` section within `ProjectileComponent` details the effects when the projectile explodes.

```xml
<config_explosion
  never_cache="1" 
  damage="0.0"
  camera_shake="0.5" 
  explosion_radius="2" 
  explosion_sprite="data/particles/explosion_008_pink.xml" 
  explosion_sprite_lifetime="0" 
  create_cell_probability="0" 
  hole_destroy_liquid="0" 
  hole_enabled="1" 
  ray_energy="400000"
  max_durability_to_destroy="8"
  particle_effect="0" 
  damage_mortals="1"
  physics_explosion_power.min="0.22"
  physics_explosion_power.max="0.3" 
  physics_throw_enabled="1" 
  shake_vegetation="1" 
  sparks_count_max="20" 
  sparks_count_min="7" 
  sparks_enabled="0"  
  material_sparks_enabled="1"
  material_sparks_count_max="2"
  material_sparks_count_min="0" 
  light_enabled="0" 
  stains_enabled="1"
  stains_radius="3" >
</config_explosion>
```

### Key Attributes:

*   **`damage`**: The damage dealt by the explosion itself. Set to `0.0`, indicating the explosion is primarily for effects rather than direct damage.
*   **`camera_shake`**: The intensity of camera shake upon explosion.
*   **`explosion_radius`**: The radius of the explosion effect.
*   **`explosion_sprite`**: The particle effect used for the explosion visual.
*   **`hole_enabled`**: If `1`, the explosion can create holes in terrain.
*   **`ray_energy`**: The energy of the explosion's destructive rays.
*   **`physics_explosion_power.min/max`**: The force applied to physics objects by the explosion.
*   **`stains_enabled`**: If `1`, the explosion leaves stains on surfaces.

## Particle Emitters

The projectile utilizes three `ParticleEmitterComponent`s to generate cosmetic effects, primarily using "plasma\_fading\_pink" material.

### Dense Emitter (Trail)

```xml
<ParticleEmitterComponent 
  emitted_material_name="plasma_fading_pink"
  count_min="1"
  count_max="4"
  lifetime_min="0.1"
  lifetime_max="0.2"
  is_trail="1"
  trail_gap="1.0"
  airflow_force="10.5"
  emission_interval_min_frames="1"
  emission_interval_max_frames="1"
  is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`is_trail="1"`**: Indicates this emitter creates a continuous trail.
*   **`trail_gap`**: Controls the spacing between trail particles.
*   **`airflow_force`**: Influences how particles react to airflow.

### Sparse Emitter

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
  trail_gap="8.0"
  airflow_force="1.5"
  emission_interval_min_frames="1"
  emission_interval_max_frames="10"
  is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`x_vel_min/max`**: Particles are emitted with horizontal velocity.
*   **`emission_interval_max_frames`**: Introduces variability in emission timing.

### Very Sparse Emitter

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
  trail_gap="8.0"
  airflow_force="0.5"
  emission_interval_min_frames="10"
  emission_interval_max_frames="20"
  is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`lifetime_min/max`**: These particles persist longer.
*   **`emission_interval_min/max_frames`**: Creates a very infrequent emission pattern.

## Lighting and Audio

### Light Component

```xml
<LightComponent 
  _enabled="1" 
  r="255"
  g="40"
  b="255"
  radius="30" >
</LightComponent>
```

*   Provides a pinkish light source with a radius of 30 units.

### Audio Component

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/bullet_light">
</AudioComponent>
```

*   Triggers the "bullet\_light" sound event from the "projectiles.bank" audio file.

## Scripting

```xml
<LuaComponent
  script_source_file="data/scripts/projectiles/commander_bullet.lua"
  execute_every_n_frame="2"
  remove_after_executed="1"
  >
</LuaComponent>
```

*   **`script_source_file`**: Links to an external Lua script (`commander_bullet.lua`) for custom logic.
*   **`execute_every_n_frame`**: The script logic executes every 2 frames.
*   **`remove_after_executed`**: The Lua component is removed after its first execution.