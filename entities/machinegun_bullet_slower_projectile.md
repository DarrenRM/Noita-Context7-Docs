---
title: Machinegun Bullet (Slower) Projectile
category: entities
---

# Machinegun Bullet (Slower) Projectile

This document details the configuration for a slower variant of the machinegun bullet projectile in Noita, intended for AI-assisted modding.

## Core Entity Configuration

The projectile is based on a default entity and primarily configured through its `ProjectileComponent`.

```xml
<Entity name="$projectile_default">

	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
			mass="0.05"
			>
    	</VelocityComponent>
	</Base>

  <ProjectileComponent
    _enabled="1"
  	lob_min="0.8"
  	lob_max="0.9"
  	speed_min="400"
  	speed_max="500"
  	friction="1.3"
  	direction_random_rad="0.1"
    on_death_explode="1"
    on_death_gfx_leave_sprite="0"
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="1"
    on_collision_die="1"
    ragdoll_force_multiplier="0.0025"
    lifetime="50"
    knockback_force="0.1"
  	velocity_sets_scale="1"
  	camera_shake_when_shot="2.0"
  	shoot_light_flash_radius="64"
  	hit_particle_force_multiplier="0.1"
    create_shell_casing="1"
    bounces_left="0"
  	damage="0.15"
	go_through_this_material="aluminium_robot"
	muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_medium.xml"
	knockback_force="0.3"
	>
    <config_explosion
      never_cache="1"
      damage="0.4"
      camera_shake="0.5"
      explosion_radius="2"
      explosion_sprite="data/particles/explosion_008.xml"
      explosion_sprite_lifetime="0"
      create_cell_probability="0"
      hole_destroy_liquid="0"
      hole_enabled="1"
      hole_image="data/temp/explosion_hole.png"
      ray_energy="400000"
      max_durability_to_destroy="9"
      particle_effect="0"
	  physics_explosion_power.min="0.08"
      physics_explosion_power.max="0.1"
      physics_throw_enabled="1"
      shake_vegetation="1"
      sparks_count_max="20"
      sparks_count_min="7"
	  material_sparks_enabled="1"
      material_sparks_count_max="2"
      material_sparks_count_min="0"
      sparks_enabled="0"
      light_enabled="0"
      stains_enabled="1"
      stains_radius="3">
    </config_explosion>
  </ProjectileComponent>

  <SpriteComponent
    _enabled="1"
    alpha="1"
    image_file="data/projectiles_gfx/bullet.xml"
    next_rect_animation=""
    rect_animation=""
    >
  </SpriteComponent>

  <AudioComponent
      file="data/audio/Desktop/projectiles.bank"
      event_root="projectiles/bullet_smg_enemy">
  </AudioComponent>

	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/machinegun_bullet_slower.xml"
		>
	</VariableStorageComponent>
</Entity>
```

## Key Projectile Attributes

These attributes within the `<ProjectileComponent>` define the behavior and impact of the projectile.

| Attribute                 | Value        | Description                                                                 |
| :------------------------ | :----------- | :-------------------------------------------------------------------------- |
| `lob_min`, `lob_max`      | `0.8`, `0.9` | Controls the minimum and maximum arc of the projectile.                     |
| `speed_min`, `speed_max`  | `400`, `500` | Defines the projectile's initial velocity range.                            |
| `friction`                | `1.3`        | How quickly the projectile loses speed due to air resistance.               |
| `direction_random_rad`    | `0.1`        | Adds a small random deviation to the projectile's initial direction.        |
| `on_death_explode`        | `1`          | Causes the projectile to explode upon death (e.g., collision, lifetime end). |
| `on_lifetime_out_explode` | `1`          | Ensures explosion when the projectile's lifetime expires.                   |
| `on_collision_die`        | `1`          | The projectile is destroyed upon colliding with an entity.                  |
| `lifetime`                | `50`         | The duration in frames before the projectile is destroyed.                  |
| `knockback_force`         | `0.3`        | The force applied to entities when hit by this projectile.                  |
| `damage`                  | `0.15`       | The base damage dealt by the projectile.                                    |
| `go_through_this_material`| `aluminium_robot` | Specifies materials the projectile can pass through without dying.          |
| `create_shell_casing`     | `1`          | Spawns a shell casing entity when the projectile is fired.                  |
| `camera_shake_when_shot`  | `2.0`        | The intensity of camera shake when this projectile is fired.                |

## Explosion Configuration

The `<config_explosion>` tag within `ProjectileComponent` details the effects when the projectile explodes.

| Attribute                 | Value        | Description                                                                 |
| :------------------------ | :----------- | :-------------------------------------------------------------------------- |
| `damage`                  | `0.4`        | Damage dealt by the explosion.                                              |
| `camera_shake`            | `0.5`        | Camera shake intensity from the explosion.                                  |
| `explosion_radius`        | `2`          | The radius of the explosion's effect.                                       |
| `explosion_sprite`        | `data/particles/explosion_008.xml` | The visual effect used for the explosion.                                   |
| `hole_enabled`            | `1`          | Whether the explosion creates holes in terrain.                             |
| `ray_energy`              | `400000`     | The energy of the explosion's destructive rays.                             |
| `physics_explosion_power` | `0.08` - `0.1` | The force applied to physics objects by the explosion.                      |
| `sparks_count_min`, `max` | `7`, `20`    | The range of sparks generated by the explosion.                             |
| `stains_enabled`          | `1`          | Whether the explosion leaves stains on surfaces.                            |
| `stains_radius`           | `3`          | The radius of the stains left by the explosion.                             |

## Visual and Audio Components

### Sprite Component

Defines the visual appearance of the projectile.

| Attribute     | Value                         | Description                               |
| :------------ | :---------------------------- | :---------------------------------------- |
| `image_file`  | `data/projectiles_gfx/bullet.xml` | The sprite asset used for the bullet.     |

### Audio Component

Handles the sound effects associated with the projectile.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.bank` | The audio bank containing projectile sounds. |
| `event_root`| `projectiles/bullet_smg_enemy`      | The specific sound event to trigger.      |