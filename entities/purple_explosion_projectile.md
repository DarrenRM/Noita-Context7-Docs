---
title: Purple Explosion Projectile
category: entities
---

# Purple Explosion Projectile

This document details the configuration for a player-owned projectile that results in a purple explosion upon death or collision.

## Entity Definition

The core of this projectile is defined by the `<Entity>` tag.

```xml
<Entity
  name="$projectile_default" tags="projectile_player"
>
  <!-- ... components ... -->
</Entity>
```

*   **`name`**: Set to `$projectile_default`, indicating it uses default projectile naming conventions.
*   **`tags`**: `projectile_player` signifies this projectile is associated with player actions.

## Base Projectile Configuration

The `<Base>` component inherits properties from `data/entities/base_projectile.xml`.

```xml
<Base file="data/entities/base_projectile.xml" >
  <VelocityComponent>
    <!-- Velocity properties are not explicitly defined here, inheriting defaults -->
  </VelocityComponent>
</Base>
```

## Projectile Component - Key Attributes

The `<ProjectileComponent>` defines the behavior and effects of the projectile.

```xml
<ProjectileComponent
  _enabled="1"
  lob_min="0.8"
  lob_max="1.0"
  speed_min="0"
  speed_max="0"
  die_on_low_velocity="1"
  on_death_explode="1"
  on_death_gfx_leave_sprite="0"
  on_lifetime_out_explode="1"
  explosion_dont_damage_shooter="0"
  on_collision_die="1"
  shoot_light_flash_radius="15"
  shoot_light_flash_r="255"
  shoot_light_flash_g="250"
  shoot_light_flash_b="80"
  damage="0"
  lifetime="0"
>
  <!-- ... config_explosion ... -->
</ProjectileComponent>
```

**Key Attributes:**

*   **`lob_min`, `lob_max`**: Controls the minimum and maximum lobbing behavior (0.8 to 1.0).
*   **`speed_min`, `speed_max`**: Set to `0`, indicating the projectile does not have inherent speed.
*   **`die_on_low_velocity`**: `1` (enabled), the projectile will die if its velocity drops too low.
*   **`on_death_explode`**: `1` (enabled), triggers an explosion when the projectile dies.
*   **`on_lifetime_out_explode`**: `1` (enabled), triggers an explosion when the projectile's lifetime expires.
*   **`on_collision_die`**: `1` (enabled), the projectile dies upon colliding with something.
*   **`shoot_light_flash_radius`, `shoot_light_flash_r`, `shoot_light_flash_g`, `shoot_light_flash_b`**: Defines a light flash effect upon shooting, with a radius of 15 and yellow-ish color.
*   **`damage`**: `0` for the projectile itself, damage is handled by the explosion.
*   **`lifetime`**: `0`, suggesting the projectile's existence is tied to other conditions (like collision or low velocity) rather than a fixed time.

### Explosion Configuration (`config_explosion`)

This nested tag defines the properties of the explosion that occurs.

```xml
<config_explosion
  never_cache="1"
  camera_shake="0"
  explosion_radius="8"
  explosion_sprite="data/particles/purple_explosion.xml"
  load_this_entity="data/entities/particles/particle_explosion/main_swirly_purple_small.xml"
  explosion_sprite_lifetime="0"
  create_cell_probability="0"
  hole_destroy_liquid="0"
  ray_energy="200000"
  damage="2.35"
  hole_enabled="1"
  hole_image="data/temp/explosion_hole.png"
  particle_effect="1"
  damage_mortals="1"
  physics_explosion_power.min="1.0"
  physics_explosion_power.max="1.5"
  physics_throw_enabled="1"
  shake_vegetation="1"
  sparks_enabled="1"
  sparks_count_max="10"
  sparks_count_min="5"
  spark_material="spark_purple_bright"
  light_fade_time="0.8"
  stains_enabled="1"
  stains_image="data/temp/explosion_stain.png"
  audio_event_name="explosions/magic_small"
>
</config_explosion>
```

**Key Explosion Attributes:**

*   **`never_cache`**: `1` (enabled), prevents caching of this explosion effect.
*   **`explosion_radius`**: `8`, the area of effect for the explosion.
*   **`explosion_sprite`**: `data/particles/purple_explosion.xml`, references the particle effect for the explosion visual.
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main_swirly_purple_small.xml`, loads a specific entity for the explosion's visual representation.
*   **`ray_energy`**: `200000`, high energy value for potential ray interactions.
*   **`damage`**: `2.35`, the damage dealt by the explosion.
*   **`hole_enabled`**: `1` (enabled), creates a hole in the environment.
*   **`particle_effect`**: `1` (enabled), activates particle effects for the explosion.
*   **`damage_mortals`**: `1` (enabled), the explosion damages living entities.
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: `1.0` to `1.5`, controls the force of the physics-based explosion.
*   **`sparks_enabled`**: `1` (enabled), generates sparks.
*   **`spark_material`**: `spark_purple_bright`, specifies the material for the sparks.
*   **`stains_enabled`**: `1` (enabled), creates stains on surfaces.
*   **`audio_event_name`**: `explosions/magic_small`, the sound effect played for the explosion.

## Variable Storage

The `<VariableStorageComponent>` stores a reference to the projectile's own file.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/deck/purple_explosion.xml"
>
</VariableStorageComponent>
```

*   **`name`**: `projectile_file`, a common identifier for storing projectile paths.
*   **`value_string`**: `data/entities/projectiles/deck/purple_explosion.xml`, the path to this entity file.