---
title: Material Gunpowder Explosive Projectile
category: entities
---

---

# Material Gunpowder Explosive Projectile

This document details the configuration for the "Material Gunpowder Explosive" projectile in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity is a player-owned projectile.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
   >
  </Entity>
```

## Projectile Component

This component defines the behavior and properties of the projectile.

### Key Attributes:

| Attribute                 | Value      | Description                                                                 |
| :------------------------ | :--------- | :-------------------------------------------------------------------------- |
| `projectile_type`         | `MATERIAL_PARTICLE` | Indicates this projectile is a material particle.                           |
| `lob_min`, `lob_max`      | `1.0`      | Controls the lobbing behavior; `1.0` suggests a straight trajectory.        |
| `speed_min`, `speed_max`  | `123`, `135` | The projectile's speed range.                                               |
| `friction`                | `3.0`      | How much the projectile's speed is reduced over time.                       |
| `on_death_emit_particle`  | `1`        | Triggers particle emission upon death.                                      |
| `on_death_emit_particle_type` | `gunpowder_explosive` | Specifies the type of particle to emit on death.                          |
| `on_death_particle_check_concrete` | `1` | Ensures particles are only emitted if the collision surface is concrete. |
| `explosion_dont_damage_shooter` | `1` | Prevents the projectile's explosion from damaging the player who fired it. |
| `die_on_liquid_collision` | `1`        | The projectile will be destroyed upon colliding with liquid.                |
| `on_collision_die`        | `1`        | The projectile will be destroyed upon any collision.                        |
| `lifetime`                | `360`      | The maximum duration of the projectile in frames.                           |
| `damage`                  | `0`        | The projectile itself deals no direct damage.                               |
| `camera_shake_when_shot`  | `1.0`      | The intensity of camera shake when this projectile is fired.                |
| `ragdoll_fx_on_collision` | `NORMAL`   | Applies a normal ragdoll effect upon collision.                             |

```xml
  <ProjectileComponent 
    _enabled="1" 
    projectile_type="MATERIAL_PARTICLE"
    lob_min="1.0"
    lob_max="1.0"
    speed_min="123"
    speed_max="135"
    friction="3.0"
    direction_random_rad="0.0"
    on_death_explode="0"
    on_death_gfx_leave_sprite="0" 
    on_lifetime_out_explode="0"
    on_death_emit_particle="1"
    on_death_emit_particle_type="gunpowder_explosive"
    on_death_particle_check_concrete="1"
    explosion_dont_damage_shooter="1" 
    die_on_liquid_collision="1"
    on_collision_die="1"
    lifetime="360"
    damage="0"
    velocity_sets_scale="1"
    lifetime_randomness="7"
    ragdoll_force_multiplier="0.01"
    hit_particle_force_multiplier="0.25 "
    camera_shake_when_shot="1.0" 
    ground_collision_fx="0"
    ragdoll_fx_on_collision="NORMAL" >
  </ProjectileComponent>
```

## Sprite Component

Defines the visual representation of the projectile.

```xml
  <SpriteComponent 
    _enabled="1" 
    alpha="1" 
    image_file="data/projectiles_gfx/dirt.xml"
     
     >
  </SpriteComponent>
```

## Variable Storage Component

Stores a reference to the projectile's own XML file.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/deck/material_gunpowder_explosive.xml"
		>
	</VariableStorageComponent>