---
title: Projectile - Material Lava
category: entities
---

# Projectile - Material Lava

This document details the configuration for the "Material Lava" projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity definition for the lava projectile.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
   >
  <Base file="data/entities/base_projectile.xml" >
  </Base>
  <VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/deck/material_lava.xml"
		>
	</VariableStorageComponent>
</Entity>
```

## ProjectileComponent

This component governs the behavior and properties of the projectile.

### Key Attributes:

| Attribute                 | Value      | Description                                                                 |
| :------------------------ | :--------- | :-------------------------------------------------------------------------- |
| `projectile_type`         | `MATERIAL_PARTICLE` | Identifies this as a material particle projectile.                          |
| `lob_min`, `lob_max`      | `1.0`      | Controls the lobbing behavior; `1.0` suggests a straight trajectory.        |
| `speed_min`, `speed_max`  | `123`-`135` | The speed range of the projectile.                                          |
| `friction`                | `3.0`      | How quickly the projectile loses speed.                                     |
| `direction_random_rad`    | `0.0`      | No randomness in the projectile's initial direction.                        |
| `on_death_emit_particle`  | `1`        | Spawns particles upon death.                                                |
| `on_death_emit_particle_type` | `lava`     | Specifies the type of particle to emit (lava).                              |
| `on_death_particle_check_concrete` | `1`        | Particles emitted on death will check for concrete surfaces.                |
| `die_on_liquid_collision` | `1`        | The projectile will be destroyed upon colliding with any liquid.            |
| `on_collision_die`        | `1`        | The projectile will be destroyed upon any collision.                        |
| `lifetime`                | `360`      | The duration in frames before the projectile is destroyed.                  |
| `damage`                  | `0`        | The projectile deals no direct damage.                                      |
| `camera_shake_when_shot`  | `1.0`      | Triggers a camera shake effect when the projectile is fired.                |
| `ragdoll_fx_on_collision` | `NORMAL`   | Applies a normal ragdoll effect upon collision.                             |

## SpriteComponent

Defines the visual representation of the projectile.

### Key Attributes:

| Attribute    | Value                         | Description                                     |
| :----------- | :---------------------------- | :---------------------------------------------- |
| `alpha`      | `1`                           | The opacity of the sprite (fully opaque).       |
| `image_file` | `data/projectiles_gfx/dirt.xml` | The sprite asset used for the projectile.       |