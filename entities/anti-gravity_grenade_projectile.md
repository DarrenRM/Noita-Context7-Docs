---
title: Anti-Gravity Grenade Projectile
category: entities
---

# Anti-Gravity Grenade Projectile

This document details the configuration for the Anti-Gravity Grenade projectile in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The projectile is defined as an `Entity` with the tag `projectile_player`. It inherits base properties from `data/entities/base_projectile.xml`.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
  <Base file="data/entities/base_projectile.xml" >
    <VelocityComponent
      mass="0.065"
      gravity_y="0"
      >
    </VelocityComponent>
  </Base>
  <!-- ... other components ... -->
</Entity>
```

### Key Attributes:

*   **`mass`**: `0.065` - Affects how the projectile interacts with physics.
*   **`gravity_y`**: `0` - Disables gravity for this projectile, contributing to its unique trajectory.

## Projectile Component

This component governs the projectile's behavior, trajectory, and effects.

```xml
<ProjectileComponent
  _enabled="1"
  lob_min="0.9"
  lob_max="1.0"
  speed_min="250"
  speed_max="280"
  friction="0.6"
  direction_random_rad="0.05"
  on_death_explode="1"
  on_death_gfx_leave_sprite="0"
  on_lifetime_out_explode="1"
  explosion_dont_damage_shooter="0"
  on_collision_die="1"
  lifetime="500"
  damage="1.0"
  velocity_sets_scale="1"
  lifetime_randomness="7"
  ragdoll_force_multiplier="0.04"
  hit_particle_force_multiplier="5.5 "
  camera_shake_when_shot="5.0"
  velocity_sets_rotation="1"
  bounces_left="4"
  muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_launcher.xml"
  shoot_light_flash_radius="120"
  shoot_light_flash_r="255"
  shoot_light_flash_g="165"
  shoot_light_flash_b="40"
  knockback_force="1.0"
  physics_impulse_coeff="3000"
  >
  <!-- ... damage_by_type and config_explosion ... -->
</ProjectileComponent>
```

### Key Attributes:

*   **`lob_min`/`lob_max`**: `0.9`/`1.0` - Controls the arc of the projectile.
*   **`speed_min`/`speed_max`**: `250`/`280` - Defines the projectile's initial velocity range.
*   **`on_death_explode`**: `1` - The projectile explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`on_collision_die`**: `1` - The projectile is destroyed upon collision.
*   **`lifetime`**: `500` - The duration in frames before the projectile expires.
*   **`damage`**: `1.0` - Base damage dealt by the projectile.
*   **`bounces_left`**: `4` - The number of times the projectile can bounce.
*   **`shoot_light_flash_radius`/`r`/`g`/`b`**: Defines the light emitted when the projectile is fired.
*   **`knockback_force`**: `1.0` - The force applied to entities when hit.
*   **`physics_impulse_coeff`**: `3000` - Coefficient for physics impulse calculations.

#### `damage_by_type`

Specifies damage multipliers against different damage types.

*   **`fire`**: `0.8` - Deals 80% of its damage as fire damage.

#### `config_explosion`

Details the explosion effect when the projectile detonates.

*   **`camera_shake`**: `10` - Intensity of camera shake during explosion.
*   **`explosion_radius`**: `7` - The radius of the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_016.xml` - The visual effect of the explosion.
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main_gunpowder_tiny.xml` - The entity spawned by the explosion.
*   **`damage`**: `1.9` - Damage dealt by the explosion itself.
*   **`physics_explosion_power.min`/`max`**: `0.3`/`0.6` - Controls the physics force of the explosion.
*   **`ray_energy`**: `350000` - Energy value for any potential ray interactions.
*   **`hole_enabled`**: `1` - Creates a hole in the environment.
*   **`stains_enabled`**: `1` - Leaves stains on surfaces.

## Sprite Component

Defines the visual appearance of the projectile.

```xml
<SpriteComponent
  _enabled="1"
  alpha="1"
  image_file="data/projectiles_gfx/grenade.xml"
  offset_x="4"
  offset_y="4"
  additive="1"
  >
</SpriteComponent>
```

### Key Attributes:

*   **`image_file`**: `data/projectiles_gfx/grenade.xml` - The sprite asset used for the projectile.
*   **`offset_x`/`offset_y`**: `4`/`4` - Adjusts the sprite's position.
*   **`additive`**: `1` - Enables additive blending for the sprite.

## Particle Emitter Components

These components control the emission of various particles to enhance visual feedback.

### Smoke Emitter

```xml
<ParticleEmitterComponent
  emitted_material_name="smoke"
  count_min="1"
  count_max="1"
  lifetime_min="0.1"
  lifetime_max="0.4"
  emission_interval_min_frames="1"
  emission_interval_max_frames="3"
  is_emitting="1"
  >
</ParticleEmitterComponent>
```

### Fire Emitter

```xml
<ParticleEmitterComponent
  emitted_material_name="fire"
  count_min="1"
  count_max="1"
  lifetime_min="0.1"
  lifetime_max="0.4"
  emission_interval_min_frames="1"
  emission_interval_max_frames="3"
  is_emitting="1" >
</ParticleEmitterComponent>
```

### Cosmetic Spark Emitter (Initial)

```xml
<ParticleEmitterComponent
  emitted_material_name="spark"
  count_min="1"
  count_max="1"
  lifetime_min="0.1"
  lifetime_max="0.3"
  create_real_particles="0"
  emit_cosmetic_particles="1"
  emission_interval_min_frames="1"
  emission_interval_max_frames="1"
  is_emitting="1" >
</ParticleEmitterComponent>
```

### Trail Spark Emitter

```xml
<ParticleEmitterComponent
  emitted_material_name="spark"
  count_min="1"
  count_max="8"
  gravity.y="-10"
  lifetime_min="0.5"
  lifetime_max="0.8"
  airflow_force="1.2"
  airflow_time="0.1"
  airflow_scale="0.03"
  is_trail="1"
  trail_gap="0.5"
  render_on_grid="1"
  fade_based_on_lifetime="1"
  create_real_particles="0"
  emit_cosmetic_particles="1"
  emission_interval_min_frames="1"
  emission_interval_max_frames="1"
  is_emitting="1"
  >
</ParticleEmitterComponent>
```

#### Key Particle Emitter Attributes:

*   **`emitted_material_name`**: Specifies the type of particle to emit (e.g., `smoke`, `fire`, `spark`).
*   **`count_min`/`max`**: The number of particles emitted per emission.
*   **`lifetime_min`/`max`**: The duration particles exist.
*   **`create_real_particles`**: `1` for physics-simulated particles, `0` for cosmetic.
*   **`is_trail`**: `1` to make particles follow a trail.
*   **`gravity.y`**: Controls vertical gravity for emitted particles.

## Audio Component

Handles the sound effects associated with the projectile.

```xml
<AudioComponent
  file="data/audio/Desktop/projectiles.bank"
  event_root="player_projectiles/bullet_launcher">
</AudioComponent>
```

## Light Component

Defines the light emitted by the projectile.

```xml
<LightComponent
  _enabled="1"
  radius="60"
  r="120"
  g="80"
  b="10">
</LightComponent>
```

### Key Attributes:

*   **`radius`**: `60` - The range of the light.
*   **`r`/`g`/`b`**: `120`/`80`/`10` - The color of the light (orange-ish).

## Lua Component

Integrates custom Lua scripting for advanced behavior.

```xml
<LuaComponent
  script_source_file="data/scripts/projectiles/grenade_anti_gravity.lua"
  execute_every_n_frame="2"
  >
</LuaComponent>
```

### Key Attributes:

*   **`script_source_file`**: `data/scripts/projectiles/grenade_anti_gravity.lua` - The path to the custom script.
*   **`execute_every_n_frame`**: `2` - The script runs every 2 frames.

## Variable Storage Component

Stores projectile-specific variables.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/deck/grenade_anti.xml"
  >
</VariableStorageComponent>
```

This component stores the path to the projectile's own entity file, useful for referencing within the game.