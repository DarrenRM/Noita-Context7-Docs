---
title: Acid Material Projectile
category: entities
---

# Acid Material Projectile

This document details the configuration for the "Acid Material" projectile in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity defines a player-owned projectile with specific behaviors and visual properties.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
   >
  <Base file="data/entities/base_projectile.xml" />
  <!-- ... ProjectileComponent, SpriteComponent, VariableStorageComponent ... -->
</Entity>
```

## ProjectileComponent - Key Attributes

This component governs the projectile's physical and behavioral aspects.

| Attribute                     | Value   | Description                                                                 |
| :---------------------------- | :------ | :-------------------------------------------------------------------------- |
| `projectile_type`             | `MATERIAL_PARTICLE` | Identifies this as a material particle projectile.                          |
| `lob_min`, `lob_max`          | `1.0`   | Controls the lobbing behavior (1.0 means no lobbing).                       |
| `speed_min`, `speed_max`      | `123`, `135` | Defines the projectile's initial speed range.                               |
| `friction`                    | `3.0`   | How quickly the projectile loses speed.                                     |
| `direction_random_rad`        | `0.0`   | No randomness in projectile direction.                                      |
| `on_death_emit_particle`      | `1`     | Emits particles upon death.                                                 |
| `on_death_emit_particle_type` | `acid`  | Specifies the type of particle to emit (acid).                              |
| `on_death_emit_particle_count`| `6`     | The number of particles emitted on death.                                   |
| `die_on_liquid_collision`     | `1`     | The projectile will be destroyed upon colliding with any liquid.            |
| `on_collision_die`            | `1`     | The projectile will be destroyed upon any collision.                        |
| `lifetime`                    | `360`   | The maximum duration of the projectile in frames.                           |
| `damage`                      | `0`     | The projectile deals no direct damage.                                      |
| `lifetime_randomness`         | `7`     | Adds a small random variation to the projectile's lifetime.                 |
| `camera_shake_when_shot`      | `1.0`   | Triggers camera shake when the projectile is fired.                         |

## SpriteComponent - Visuals

This component defines the visual representation of the projectile.

| Attribute   | Value                         | Description                               |
| :---------- | :---------------------------- | :---------------------------------------- |
| `alpha`     | `1`                           | Full opacity.                             |
| `image_file`| `data/projectiles_gfx/dirt.xml` | Uses a sprite defined in `dirt.xml`.      |

## VariableStorageComponent

Stores a reference to the projectile's own XML file.

| Attribute     | Value                                   | Description                               |
| :------------ | :-------------------------------------- | :---------------------------------------- |
| `name`        | `projectile_file`                       | The name of the variable.                 |
| `value_string`| `data/entities/projectiles/deck/material_acid.xml` | The path to this projectile's definition. |