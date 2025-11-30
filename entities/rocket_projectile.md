---
title: Rocket Projectile
category: entities
---

# Rocket Projectile

This document details the configuration for the "rocket" projectile entity in Noita, designed for AI-assisted modding.

## Core Components

The rocket projectile is defined by several key components that govern its behavior, appearance, and effects.

### Entity Definition

```xml
<Entity name="$projectile_default" tags="projectile_player,rocket" >
```

*   **`name`**: `$projectile_default` - A placeholder name, typically overridden by specific projectile definitions.
*   **`tags`**: `projectile_player,rocket` - Identifies this entity as a player projectile and specifically as a rocket.

### Base Projectile Configuration

```xml
<Base file="data/entities/base_projectile.xml" >
    <VelocityComponent
        gravity_y="50"
        air_friction="-5.0"
		mass="0.05"
		>
    </VelocityComponent>
</Base>
```

*   **`VelocityComponent`**:
    *   `gravity_y`: `50` - Controls the downward acceleration due to gravity.
    *   `air_friction`: `-5.0` - Represents the resistance to movement in the air.
    *   `mass`: `0.05` - The mass of the projectile, influencing its interaction with physics.

### Projectile Behavior (`ProjectileComponent`)

This is the primary component defining the rocket's projectile-specific attributes.

```xml
<ProjectileComponent
    _enabled="1"
    lob_min="0.8"
    lob_max="1.0"
    speed_min="70"
    speed_max="100"
    direction_random_rad="0.0"
    on_death_explode="1"
    on_death_gfx_leave_sprite="0"
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="0"
    on_collision_die="1"
    lifetime="360"
    damage="3"
    velocity_sets_scale="1"
    lifetime_randomness="7"
    ragdoll_force_multiplier="0.04"
    hit_particle_force_multiplier="5.5 "
    camera_shake_when_shot="15.0"
	muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_launcher.xml"
    shoot_light_flash_r="255"
    shoot_light_flash_g="210"
    shoot_light_flash_b="40"
    shoot_light_flash_radius="90"
	knockback_force="3.0"
	physics_impulse_coeff="3000"
	>
    <config_explosion
      never_cache="1"
      camera_shake="20"
      explosion_radius="15"
      explosion_sprite="data/particles/explosion_032.xml"
      explosion_sprite_lifetime="0"
      load_this_entity="data/entities/particles/particle_explosion/main_small.xml"
      create_cell_probability="10"
      cell_explosion_power_ragdoll_coeff="0.5"
      hole_destroy_liquid="0"
      explosion_sprite_additive="1"
      hole_enabled="1"
      ray_energy="4000000"
      damage="4.2"
      particle_effect="1"
      damage_mortals="1"
      physics_explosion_power.min="1.0"
      physics_explosion_power.max="1.4"
      physics_throw_enabled="1"
      shake_vegetation="1"
      sparks_count_max="20"
      sparks_count_min="7"
      sparks_enabled="1"
      stains_enabled="1"
      stains_radius="15"
      audio_event_name="explosions/magic_rocket_small" >
    </config_explosion>
</ProjectileComponent>
```

*   **`lob_min`, `lob_max`**: `0.8`, `1.0` - Controls the minimum and maximum lobbing behavior (arc of the projectile).
*   **`speed_min`, `speed_max`**: `70`, `100` - The range of initial projectile speeds.
*   **`direction_random_rad`**: `0.0` - No randomness in the initial projectile direction.
*   **`on_death_explode`**: `1` - The projectile explodes upon death (e.g., hitting a target or running out of lifetime).
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`on_collision_die`**: `1` - The projectile is destroyed upon collision.
*   **`lifetime`**: `360` - The maximum duration (in frames) the projectile exists before expiring.
*   **`damage`**: `3` - The base damage dealt by the projectile itself.
*   **`camera_shake_when_shot`**: `15.0` - The intensity of camera shake when the projectile is fired.
*   **`muzzle_flash_file`**: `data/entities/particles/muzzle_flashes/muzzle_flash_launcher.xml` - Specifies the particle effect for the muzzle flash.
*   **`shoot_light_flash_r/g/b/radius`**: `255, 210, 40, 90` - Defines the color and radius of the light flash when the projectile is shot.
*   **`knockback_force`**: `3.0` - The force applied to knock back entities upon impact.
*   **`physics_impulse_coeff`**: `3000` - Coefficient for physics impulse, affecting how it interacts with physics objects.
*   **`config_explosion`**:
    *   `camera_shake`: `20` - Camera shake intensity upon explosion.
    *   `explosion_radius`: `15` - The radius of the explosion's effect.
    *   `explosion_sprite`: `data/particles/explosion_032.xml` - The visual sprite for the explosion.
    *   `load_this_entity`: `data/entities/particles/particle_explosion/main_small.xml` - The entity to load for the explosion effect.
    *   `ray_energy`: `4000000` - The energy of the explosion's damaging rays.
    *   `damage`: `4.2` - The damage dealt by the explosion.
    *   `physics_explosion_power.min/max`: `1.0`, `1.4` - The minimum and maximum power of the physics-based explosion force.
    *   `sparks_count_min/max`: `7`, `20` - The range for the number of sparks generated by the explosion.
    *   `audio_event_name`: `explosions/magic_rocket_small` - The sound event triggered by the explosion.

### Visual Representation (`SpriteComponent`)

```xml
<SpriteComponent
    _enabled="1"
    alpha="1"
    image_file="data/projectiles_gfx/fireball_small.xml"
    >
</SpriteComponent>
```

*   **`image_file`**: `data/projectiles_gfx/fireball_small.xml` - Specifies the graphical asset used for the projectile's sprite.

### Lighting (`LightComponent`)

```xml
<LightComponent
    _enabled="1"
    r="255"
    g="100"
    b="10"
    radius="150" >
</LightComponent>
```

*   **`r`, `g`, `b`**: `255, 100, 10` - Defines the red, green, and blue components of the light emitted by the projectile.
*   **`radius`**: `150` - The radius of the light emitted.

### Particle Emitters

The rocket utilizes multiple `ParticleEmitterComponent` instances to generate various visual effects.

#### Smoke Emitter

```xml
<ParticleEmitterComponent
    emitted_material_name="smoke"
    offset.x="0"
    offset.y="0"
    x_pos_offset_min="-1"
    y_pos_offset_min="-1"
    x_pos_offset_max="1"
    y_pos_offset_max="1"
    x_vel_min="-10"
    x_vel_max="10"
    y_vel_min="-10"
    y_vel_max="10"
    count_min="5"
    count_max="5"
    lifetime_min="0.1"
    lifetime_max="0.3"
    create_real_particles="1"
    emit_cosmetic_particles="0"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: `smoke` - The type of particle to emit.
*   **`count_min/max`**: `5` - Emits a fixed number of smoke particles per emission.
*   **`lifetime_min/max`**: `0.1`, `0.3` - The duration each smoke particle exists.

#### Spark Emitters (Multiple)

There are several identical spark emitters with varying gravity settings, creating a trail of sparks.

```xml
<!-- Example of one spark emitter -->
<ParticleEmitterComponent
    emitted_material_name="spark"
    offset.x="0"
    offset.y="0"
    count_min="1"
    count_max="8"
    gravity.y="10"  <!-- Varies across emitters -->
    lifetime_min="0.3"
    lifetime_max="0.5"
    airflow_force="0.6"
    airflow_time="0.1"
    airflow_scale="0.03"
    is_trail="1"
    trail_gap="0.5"
    render_on_grid="1"
    fade_based_on_lifetime="1"
    create_real_particles="0"
    emit_cosmetic_particles="1"
    emission_interval_min_frames="1"
    emission_interval_max_frames="2"
    is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: `spark` - Emits spark particles.
*   **`count_min/max`**: `1`, `8` - The number of sparks emitted per interval.
*   **`gravity.y`**: Varies (`10`, `-10`, `0.0`) across different emitters to control spark trajectory.
*   **`lifetime_min/max`**: `0.3`, `0.5` - The duration each spark particle exists.
*   **`is_trail`**: `1` - Indicates these are trail particles.
*   **`trail_gap`**: `0.5` - The spacing between trail particles.

#### Sparse Spark Emitter

```xml
<!-- very sparse emitter -->
<ParticleEmitterComponent
    emitted_material_name="spark"
    offset.x="0"
    offset.y="0"
    x_pos_offset_min="0"
    x_pos_offset_max="0"
    y_pos_offset_min="0"
    y_pos_offset_max="0"
    x_vel_min="10"
    x_vel_max="20"
    y_vel_min="0"
    y_vel_max="0"
    gravity.y="0.0"
    count_min="1"
    count_max="1"
    lifetime_min="1.4"
    lifetime_max="1.5"
    is_trail="0"
    trail_gap="8.0"
    render_on_grid="1"
    fade_based_on_lifetime="1"
    airflow_force="0.5"
    airflow_time="0.5"
    airflow_scale="0.05"
    emission_interval_min_frames="8"
    emission_interval_max_frames="12"
    emit_cosmetic_particles="1"
    create_real_particles="0"
    is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emission_interval_min_frames/max_frames`**: `8`, `12` - Emits sparks less frequently.
*   **`lifetime_min/max`**: `1.4`, `1.5` - Sparks have a longer lifespan.
*   **`is_trail`**: `0` - These are not trail particles.

### Audio (`AudioComponent`)

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/bullet_rocket">
</AudioComponent>
```

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound effects.
*   **`event_root`**: `player_projectiles/bullet_rocket` - The specific sound event to trigger.

### Variable Storage (`VariableStorageComponent`)

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/deck/rocket.xml"
    >
</VariableStorageComponent>
```

*   **`name`**: `projectile_file` - Stores the path to this projectile's XML definition.
*   **`value_string`**: `data/entities/projectiles/deck/rocket.xml` - The actual file path.