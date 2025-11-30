---
title: Oil Projectile
category: entities
---

# Oil Projectile

This document details the configuration for the "Oil" projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity is defined as a player projectile.

```xml
<Entity
  name="$projectile_default" tags="projectile_player"
>
  <Base file="data/entities/base_projectile.xml" />
  <!-- ... other components ... -->
</Entity>
```

## ProjectileComponent - Key Attributes

This component governs the behavior and properties of the projectile.

| Attribute                  | Value   | Description                                                                 |
| :------------------------- | :------ | :-------------------------------------------------------------------------- |
| `projectile_type`          | `MATERIAL_PARTICLE` | Identifies this as a material particle projectile.                          |
| `lob_min`, `lob_max`       | `1.0`   | Controls the lobbing behavior (no lobbing in this case).                    |
| `speed_min`, `speed_max`   | `123-135` | The projectile's speed range.                                               |
| `friction`                 | `3.0`   | How quickly the projectile loses speed.                                     |
| `direction_random_rad`     | `0.0`   | No initial random deviation in direction.                                   |
| `on_death_emit_particle`   | `1`     | Emits particles upon death.                                                 |
| `on_death_emit_particle_type` | `oil`   | Specifies the type of particle to emit (oil).                               |
| `die_on_liquid_collision`  | `1`     | The projectile will be destroyed upon colliding with any liquid.            |
| `on_collision_die`         | `1`     | The projectile will be destroyed upon any collision.                        |
| `lifetime`                 | `360`   | The projectile's lifespan in frames.                                        |
| `damage`                   | `0`     | This projectile deals no direct damage.                                     |
| `camera_shake_when_shot`   | `1.0`   | Applies a camera shake effect when the projectile is fired.                 |

## SpriteComponent

Defines the visual representation of the projectile.

```xml
<SpriteComponent
  _enabled="1"
  alpha="1"
  image_file="data/projectiles_gfx/dirt.xml"
>
</SpriteComponent>
```

*   `image_file`: Points to the sprite definition for the projectile's appearance.

## VariableStorageComponent

Stores a reference to the projectile's own XML file.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/deck/material_oil.xml"
>
</VariableStorageComponent>
```