---
title: Teleport Projectile Closer
category: entities
---

---

# Teleport Projectile Closer

This document details the configuration for the `teleport_projectile_closer.xml` entity in Noita, designed for AI-assisted modding. This projectile is characterized by its teleportation behavior and its ability to draw the player closer upon impact.

## Core Components

### Entity Definition

The main entity definition sets up the projectile with specific tags and inherits from a base projectile.

```xml
<Entity name="$projectile_default" tags="projectile_player,teleport_projectile_closer" >
    <Base file="data/entities/base_projectile.xml" >
        <VelocityComponent
          gravity_y="200"
          air_friction="1.7"
          mass="0.04"
          >
        </VelocityComponent>
    </Base>
    <!-- ... other components ... -->
</Entity>
```

### Projectile Component

This is the primary component defining the projectile's behavior, including its trajectory, impact effects, and special properties.

*   **`lob_min`, `lob_max`**: Controls the minimum and maximum lob angle (in radians) for the projectile's trajectory.
*   **`speed_min`, `speed_max`**: Defines the range of initial speeds for the projectile.
*   **`on_death_explode`**: If `1`, the projectile explodes when it dies.
*   **`on_lifetime_out_explode`**: If `1`, the projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: If `1`, the explosion will not harm the entity that fired it.
*   **`on_collision_die`**: If `1`, the projectile dies upon collision.
*   **`lifetime`**: The duration (in frames) the projectile exists before expiring.
*   **`damage`**: The amount of damage the projectile deals. Set to `0` for this projectile.
*   **`friendly_fire`**: If `1`, the projectile can damage friendly entities.
*   **`collide_with_shooter_frames`**: Number of frames the projectile will ignore collisions with its shooter.
*   **`lifetime_randomness`**: Adds randomness to the projectile's lifetime.
*   **`muzzle_flash_file`**: Specifies the particle effect for the muzzle flash.
*   **`shoot_light_flash_radius`, `shoot_light_flash_r`, `shoot_light_flash_g`, `shoot_light_flash_b`**: Define the properties of the light flash when the projectile is shot.

#### `config_explosion`

Nested within `ProjectileComponent`, this defines the properties of the explosion that occurs upon death or lifetime expiry.

*   **`damage`**: The damage dealt by the explosion. Set to `0.0` here.
*   **`camera_shake`**: The intensity of camera shake caused by the explosion.
*   **`explosion_radius`**: The radius of the explosion.
*   **`explosion_sprite`**: The particle effect used for the explosion.
*   **`hole_enabled`**: If `1`, the explosion creates holes in the environment.
*   **`ray_energy`**: The energy of the explosion's rays.
*   **`damage_mortals`**: If `1`, the explosion damages mortal entities.
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: Controls the physics force of the explosion. Set to `0` to disable physics impact.
*   **`stains_enabled`**: If `1`, the explosion leaves stains.
*   **`stains_radius`**: The radius of the stains left by the explosion.

### Sprite Component

Defines the visual representation of the projectile. In this case, `image_file` is empty, suggesting it might rely on particle effects or other visual elements.

```xml
<SpriteComponent
  _enabled="1"
  alpha="1"
  image_file=""
  >
</SpriteComponent>
```

### Audio Component

Handles the sound effects associated with the projectile.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/teleport">
</AudioComponent>
```

### Particle Emitter Components

These components generate various particle effects to enhance the visual feedback of the projectile.

*   **First `ParticleEmitterComponent`**:
    *   `emitted_material_name`: `spark_purple_bright`
    *   `count_min`, `count_max`: `1` to `2`
    *   `lifetime_min`, `lifetime_max`: `0.4` to `1.8`
    *   `is_trail`: `1` (indicates a trail effect)
    *   `airflow_force`, `airflow_time`, `airflow_scale`: Control airflow dynamics for particles.
    *   `emit_cosmetic_particles`: `1` (emits cosmetic particles)

*   **Second `ParticleEmitterComponent`**:
    *   `emitted_material_name`: `spark_purple_bright`
    *   `count_min`, `count_max`: `70` to `140`
    *   `lifetime_min`, `lifetime_max`: `0.4` to `0.6`
    *   `is_trail`: `1`
    *   `airflow_force`, `airflow_time`, `airflow_scale`: Control airflow dynamics.

*   **`SpriteParticleEmitterComponent`**:
    *   `sprite_file`: `data/particles/shine_02.xml`
    *   `lifetime`: `2`
    *   `color.r`, `color.g`, `color.b`, `color.a`: Initial color of the sprite particles.
    *   `color_change.r`, `color_change.g`, `color_change.b`, `color_change.a`: How the color changes over time.
    *   `gravity.y`: `10` (particles are affected by gravity)
    *   `count_min`, `count_max`: `1` to `2`
    *   `randomize_rotation`, `randomize_angular_velocity`: Controls random rotation and angular velocity.
    *   `randomize_position`: Controls random initial positioning.

### Variable Storage Components

These components store custom variables that can be accessed by scripts.

*   **`projectile_file`**: Stores the path to this projectile's XML file.
*   **`origin_x`, `origin_y`**: Stores the origin coordinates, tagged with `teleport_closer`.

### Lua Component

This component executes a Lua script upon the entity's addition, likely for initialization or specific projectile logic.

```xml
<LuaComponent
    script_source_file="data/scripts/projectiles/teleport_projectile_closer_init.lua"
    execute_on_added="1"
    remove_after_executed="1"
    >
</LuaComponent>
```

### Hit Effect Component

Defines the effect that occurs when the projectile hits something.

```xml
<HitEffectComponent
    effect_hit="LOAD_ENTITY"
    value_string="data/entities/misc/teleport_projectile_closer_hit.xml" >
</HitEffectComponent >
```
This indicates that upon hitting, another entity (`teleport_projectile_closer_hit.xml`) is loaded, likely responsible for the "draw player closer" effect.