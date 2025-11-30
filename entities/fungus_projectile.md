---
title: Fungus Projectile
category: entities
---

# Fungus Projectile

This document describes the `fungus.xml` entity, which defines a projectile fired by the Fungus enemy in Noita.

## Core Entity

The `Entity` tag defines the base object.

```xml
<Entity
  name="$projectile_default"
>
  </Entity>
```

## Base Projectile Configuration

The `Base` tag inherits properties from the default projectile.

### VelocityComponent

Defines the physical properties of the projectile.

| Attribute | Value | Description |
|---|---|---|
| `mass` | `1.4` | The mass of the projectile. |

```xml
<Base file="data/entities/base_projectile.xml">
  <VelocityComponent
    mass="1.4"
  >
  </VelocityComponent>
</Base>
```

## Projectile Component

The `ProjectileComponent` governs the behavior and effects of the projectile.

### Key Attributes

| Attribute | Value | Description |
|---|---|---|
| `_enabled` | `1` | Enables the projectile component. |
| `lob_min`, `lob_max` | `0.5`, `1.0` | Controls the minimum and maximum lob (arc) of the projectile. |
| `speed_min`, `speed_max` | `200`, `340` | Sets the minimum and maximum initial speed of the projectile. |
| `friction` | `1` | The amount of friction applied to the projectile. |
| `direction_random_rad` | `0.02` | Adds a small random deviation to the projectile's direction in radians. |
| `on_death_explode` | `0` | Prevents the projectile from exploding upon death. |
| `on_death_gfx_leave_sprite` | `0` | Prevents the projectile from leaving a sprite upon death. |
| `on_lifetime_out_explode` | `0` | Prevents the projectile from exploding when its lifetime expires. |
| `explosion_dont_damage_shooter` | `1` | Ensures the projectile's explosion (if any) does not damage the shooter. |
| `lifetime` | `-1` | The projectile has an indefinite lifetime. |
| `hit_particle_force_multiplier` | `0.1` | Multiplier for particle force upon collision. |
| `damage` | `0.0` | The projectile deals no direct damage. |
| `on_collision_die` | `1` | The projectile dies upon collision. |
| `on_collision_spawn_entity` | `1` | Spawns another entity upon collision. |
| `spawn_entity` | `data/entities/misc/fungus_projectile.xml` | The entity to spawn upon collision (a secondary fungus projectile effect). |

```xml
<ProjectileComponent
  _enabled="1"
  lob_min="0.5"
  lob_max="1.0"
  speed_min="200"
  speed_max="340"
  angular_velocity="0"
  friction="1"
  direction_random_rad="0.02"
  on_death_explode="0"
  on_death_gfx_leave_sprite="0"
  on_lifetime_out_explode="0"
  explosion_dont_damage_shooter="1"
  ragdoll_force_multiplier="0.005"
  lifetime="-1"
  camera_shake_when_shot="0"
  shoot_light_flash_radius="0"
  hit_particle_force_multiplier="0.1"
  damage="0.0"
  velocity_sets_rotation="0"
  velocity_sets_scale="0"
  on_collision_die="1"
  on_collision_spawn_entity="1"
  spawn_entity="data/entities/misc/fungus_projectile.xml"
>
</ProjectileComponent>
```

## Sprite Component

Defines the visual representation of the projectile.

### Key Attributes

| Attribute | Value | Description |
|---|---|---|
| `image_file` | `data/enemies_gfx/fungus.xml` | Specifies the sprite image to use. |
| `offset_x`, `offset_y` | `6`, `12` | Adjusts the sprite's position relative to the entity's origin. |
| `rect_animation` | `walk` | Uses the "walk" animation from the specified image file. |

```xml
<SpriteComponent
  image_file="data/enemies_gfx/fungus.xml"
  offset_x="6"
  offset_y="12"
  rect_animation="walk"
>
</SpriteComponent>
```