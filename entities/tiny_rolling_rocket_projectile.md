---
title: Tiny Rolling Rocket Projectile
category: entities
---

# Tiny Rolling Rocket Projectile

This document details the configuration for a small, rolling rocket projectile in Noita, designed for AI-assisted modding.

## Entity Definition

The core of the projectile is defined by the `<Entity>` tag.

```xml
<Entity
  name="$projectile_default"
>
  <!-- ... components ... -->
</Entity>
```

## Base Projectile Configuration

The `<Base>` tag inherits properties from the default projectile.

### Velocity Component

Controls the projectile's movement characteristics.

```xml
<Base file="data/entities/base_projectile.xml">
  <VelocityComponent
    gravity_y="250"      <!-- Vertical acceleration due to gravity -->
    air_friction="0.6">  <!-- Resistance from air -->
  </VelocityComponent>
</Base>
```

## Projectile Component

This component defines the specific behaviors and attributes of the tiny rolling rocket.

### Key Attributes:

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `_enabled`                | `1`     | Enables this component.                                                     |
| `lob_min`, `lob_max`      | `0.5`, `0.9` | Minimum and maximum lob angle (vertical deviation) for the projectile.      |
| `speed_min`, `speed_max`  | `80`, `150` | Minimum and maximum initial speed of the projectile.                        |
| `friction`                | `1`     | How much friction affects the projectile's speed.                           |
| `direction_random_rad`    | `0.01`  | Small random deviation in projectile direction.                             |
| `on_death_explode`        | `0`     | Does not explode upon death.                                                |
| `on_death_gfx_leave_sprite` | `0`     | Does not leave a sprite upon death.                                         |
| `on_lifetime_out_explode` | `0`     | Does not explode when its lifetime expires.                                 |
| `explosion_dont_damage_shooter` | `1`     | The projectile's explosion (if any) will not damage the shooter.            |
| `on_collision_die`        | `1`     | The projectile dies upon collision.                                         |
| `on_collision_remove_projectile` | `0`     | Does not remove itself upon collision (it dies instead).                    |
| `on_collision_spawn_entity` | `1`     | Spawns another entity upon collision.                                       |
| `spawn_entity`            | `data/entities/projectiles/rocket_tiny.xml` | The entity to spawn upon collision (a smaller rocket).                      |
| `spawn_entity_is_projectile` | `1`     | The spawned entity is also a projectile.                                    |
| `lifetime`                | `55`    | Base lifetime of the projectile in frames.                                  |
| `damage`                  | `0`     | Base damage dealt by the projectile.                                        |
| `lifetime_randomness`     | `7`     | Random variation added to the projectile's lifetime.                        |
| `die_on_low_velocity`     | `1`     | The projectile dies if its velocity drops below a certain limit.            |
| `die_on_low_velocity_limit` | `5`     | The velocity limit for `die_on_low_velocity`.                               |
| `bounce_always`           | `1`     | The projectile will always bounce off surfaces.                             |
| `collide_with_shooter_frames` | `6`     | Frames the projectile will ignore collisions with its shooter.              |
| `velocity_sets_rotation`  | `1`     | The projectile's rotation is updated based on its velocity.                 |
| `muzzle_flash_file`       | `data/entities/particles/muzzle_flashes/muzzle_flash_large.xml` | Particle effect for the muzzle flash. |

```xml
<ProjectileComponent
  _enabled="1"
  lob_min="0.5"
  lob_max="0.9"
  speed_min="80"
  speed_max="150"
  friction="1"
  direction_random_rad="0.01"
  on_death_explode="0"
  on_death_gfx_leave_sprite="0"
  on_lifetime_out_explode="0"
  explosion_dont_damage_shooter="1"
  on_collision_die="1"
  on_collision_remove_projectile="0"
  on_collision_spawn_entity="1"
  spawn_entity="data/entities/projectiles/rocket_tiny.xml"
  spawn_entity_is_projectile="1"
  lifetime="55"
  damage="0"
  lifetime_randomness="7"
  ragdoll_force_multiplier="0"
  hit_particle_force_multiplier="0.1"
  create_shell_casing="0"
  muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_large.xml"
  shoot_light_flash_radius="0"
  die_on_low_velocity="1"
  die_on_low_velocity_limit="5"
  bounce_always="1"
  collide_with_shooter_frames="6"
  velocity_sets_rotation="1"
  velocity_updates_animation="0"
  velocity_sets_scale="0"
>
  <config_explosion>
  </config_explosion>
</ProjectileComponent>
```

## Sprite Component

Defines the visual appearance of the projectile.

```xml
<SpriteComponent
  _enabled="1"
  alpha="1"
  image_file="data/projectiles_gfx/rocket_tiny.xml"
  next_rect_animation=""
  rect_animation=""
>
</SpriteComponent>
```

*   `image_file`: Specifies the sprite sheet or animation definition.

## Audio Component

Handles the sound effects associated with the projectile.

```xml
<AudioComponent
  file="data/audio/Desktop/projectiles.bank"
  event_root="projectiles/rocket_tiny_roll" >
</AudioComponent>
```

*   `file`: The Wwise audio bank containing the sound events.
*   `event_root`: The specific sound event to trigger for this projectile.