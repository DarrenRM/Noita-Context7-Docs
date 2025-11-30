---
title: Fizzle Projectile
category: entities
---

# Fizzle Projectile

This document details the configuration of the "Fizzle" projectile entity in Noita, intended for AI-assisted modding.

## Entity Definition

The core entity definition for the Fizzle projectile.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
  <!-- ... components ... -->
</Entity>
```

*   **`name`**: `$projectile_default` - A placeholder name, typically overridden by specific projectile types.
*   **`tags`**: `projectile_player` - Indicates this projectile is fired by the player.

## Base Projectile Configuration

Inherits fundamental projectile properties.

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

*   **`gravity_y`**: `200` - The strength of gravity affecting the projectile.
*   **`air_friction`**: `2.7` - Resistance from air.
*   **`mass`**: `0.02` - The projectile's mass.

## Projectile Component - Key Attributes

This component governs the projectile's behavior, trajectory, and interactions.

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
  lifetime="20"
  damage="0.18"
  bounce_always="1"
  bounces_left="10"
  bounce_energy="0.6"
  bounce_fx_file="data/entities/particles/bounce_effects/fizzle.xml"
  velocity_sets_scale="1"
  lifetime_randomness="12"
  ragdoll_force_multiplier="0.05"
  hit_particle_force_multiplier="0.3"
  velocity_sets_rotation="1"
  shoot_light_flash_radius="80"
  shoot_light_flash_r="50"
  shoot_light_flash_g="50"
  shoot_light_flash_b="50"
  knockback_force="1.0"
  physics_impulse_coeff="2500"
  >
  <!-- ... config_explosion ... -->
</ProjectileComponent>
```

*   **`lob_min`, `lob_max`**: `0.5`, `0.7` - Controls the arc of the projectile.
*   **`speed_min`, `speed_max`**: `600`, `800` - The range of initial projectile speeds.
*   **`on_death_explode`**: `1` - The projectile explodes when it dies (e.g., from lifetime out or collision).
*   **`on_lifetime_out_explode`**: `1` - Explodes when its lifetime expires.
*   **`on_collision_die`**: `1` - Dies upon colliding with something.
*   **`lifetime`**: `20` - The base duration in seconds before expiring.
*   **`damage`**: `0.18` - The base damage dealt by the projectile.
*   **`bounce_always`**: `1` - The projectile will always attempt to bounce.
*   **`bounces_left`**: `10` - The maximum number of bounces allowed.
*   **`bounce_energy`**: `0.6` - The energy retained after each bounce.
*   **`bounce_fx_file`**: `data/entities/particles/bounce_effects/fizzle.xml` - Specifies the particle effect for bounces.
*   **`lifetime_randomness`**: `12` - Adds random variation to the projectile's lifetime.
*   **`knockback_force`**: `1.0` - The force applied to knock back entities on impact.

### `config_explosion`

Defines the properties of the explosion when the projectile dies.

```xml
<config_explosion
  never_cache="1"
  damage="0.0"
  camera_shake="0"
  explosion_radius="2"
  create_cell_probability="0"
  hole_destroy_liquid="0"
  hole_enabled="0"
  ray_energy="400000"
  particle_effect="0"
  damage_mortals="1"
  physics_explosion_power.min="0"
  physics_explosion_power.max="0"
  physics_throw_enabled="0"
  shake_vegetation="1"
  sparks_enabled="0"
  material_sparks_enabled="1"
  material_sparks_count_max="2"
  material_sparks_count_min="0"
  light_enabled="0"
  stains_enabled="1"
  stains_radius="3" >
</config_explosion>
```

*   **`damage`**: `0.0` - The explosion itself deals no direct damage.
*   **`explosion_radius`**: `2` - The radius of the explosion effect.
*   **`ray_energy`**: `400000` - The energy of the explosion's raycast.
*   **`damage_mortals`**: `1` - The explosion can damage living entities.
*   **`shake_vegetation`**: `1` - The explosion can affect vegetation.
*   **`material_sparks_enabled`**: `1` - Enables sparks from destroyed materials.
*   **`stains_enabled`**: `1` - Enables stains on surfaces.
*   **`stains_radius`**: `3` - The radius of the stains.

## Audio Component

Defines the sound effects associated with the projectile.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/fizzle">
</AudioComponent>
```

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
*   **`event_root`**: `player_projectiles/fizzle` - The specific sound event to trigger.

## Light Component

Adds a light source when the projectile is active.

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

*   **`radius`**: `60` - The radius of the light.
*   **`fade_out_time`**: `0.1` - How quickly the light fades.
*   **`r`, `g`, `b`**: `40`, `80`, `10` - The RGB color values of the light.

## Particle Emitter Components

These components generate visual particle effects.

### Emitter 1 (Main Trail/Impact)

```xml
<ParticleEmitterComponent
  emitted_material_name="spark_white"
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

*   **`emitted_material_name`**: `spark_white` - The material used for the particles.
*   **`count_min`, `count_max`**: `1`, `6` - The number of particles emitted per interval.
*   **`lifetime_min`, `lifetime_max`**: `0.6`, `1.1` - The duration particles exist.
*   **`gravity.y`**: `20` - Gravity affecting these particles.

### Emitter 2 (Secondary/Upward Burst)

```xml
<ParticleEmitterComponent
  emitted_material_name="spark_white"
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

*   **`gravity.y`**: `-10` - These particles are affected by upward gravity.
*   **`airflow_force`, `airflow_time`, `airflow_scale`**: These parameters influence how particles react to air currents.

## Lua Component

Integrates custom Lua scripting for advanced behavior.

```xml
<LuaComponent
    script_source_file="data/scripts/projectiles/chaotic_arc.lua"
    execute_every_n_frame="2"
    >
</LuaComponent>
```

*   **`script_source_file`**: `data/scripts/projectiles/chaotic_arc.lua` - The path to the Lua script.
*   **`execute_every_n_frame`**: `2` - The script logic runs every 2 frames.

## Variable Storage Component

Stores persistent variables associated with the entity.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/deck/fizzle.xml"
    >
</VariableStorageComponent>
```

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/deck/fizzle.xml` - The value, referencing its own entity file.