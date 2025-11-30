---
title: Boss Pit Wand Projectile
category: entities
---

# Boss Pit Wand Projectile

This document details the configuration of the projectile fired by the Boss Pit Wand in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The projectile is based on a default projectile entity, inheriting its fundamental properties.

```xml
<Entity 
	name="$projectile_default" 
	>
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
			gravity_y="0"
			air_friction="4"
			mass="0.05"
			>
		</VelocityComponent> 
	</Base>
    <!-- ... other components ... -->
</Entity>
```

## Projectile Component - Key Attributes

This component defines the projectile's behavior, including its trajectory, damage, and interaction with the environment.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `_enabled`                | `1`     | Enables the projectile component.                                           |
| `lob_min`, `lob_max`      | `0.8`, `1.0` | Controls the projectile's lobbing behavior (arc).                           |
| `speed_min`, `speed_max`  | `60`    | Sets the projectile's speed.                                                |
| `die_on_low_velocity`     | `0`     | Projectile does not die if its velocity becomes too low.                    |
| `on_death_explode`        | `1`     | The projectile explodes upon death.                                         |
| `on_lifetime_out_explode` | `1`     | The projectile explodes when its lifetime expires.                          |
| `explosion_dont_damage_shooter` | `1` | The explosion does not damage the entity that fired the projectile.         |
| `damage`                  | `0.8`   | The base damage dealt by the projectile's explosion.                        |
| `lifetime`                | `180`   | The duration in frames before the projectile explodes if not otherwise killed. |
| `penetrate_entities`      | `1`     | The projectile can pass through multiple entities.                          |

### `config_explosion` - Detailed Breakdown

This nested element defines the properties of the explosion that occurs when the projectile dies.

| Attribute                 | Value        | Description                                                                 |
| :------------------------ | :----------- | :-------------------------------------------------------------------------- |
| `never_cache`             | `1`          | Prevents the explosion from being cached, ensuring unique instances.         |
| `camera_shake`            | `0`          | Disables camera shake upon explosion.                                       |
| `explosion_radius`        | `32`         | The radius of the explosion effect.                                         |
| `explosion_sprite`        | `...plasma.xml` | The visual sprite used for the explosion.                                   |
| `ray_energy`              | `5000`       | Energy value associated with the explosion's ray effects.                   |
| `hole_destroy_liquid`     | `1`          | The explosion can destroy liquids.                                          |
| `hole_enabled`            | `1`          | Enables the creation of holes in terrain by the explosion.                  |
| `hole_image`              | `...hole.png` | The image used for the terrain hole created by the explosion.               |
| `physics_explosion_power` | `0.3` - `0.4` | The minimum and maximum power of the physics-based explosion force.         |
| `shake_vegetation`        | `1`          | The explosion can shake vegetation.                                         |
| `light_r`, `light_g`, `light_b` | `15`, `15`, `40` | The RGB values for the light emitted by the explosion.                      |

## Sprite Component

Defines the visual appearance of the projectile.

```xml
	<SpriteComponent 
		_enabled="1" 
		alpha="1" 
		image_file="data/entities/animals/boss_pit/wand_0$[1-9].png" 
		offset_x="16" 
		offset_y="16"
		>
	</SpriteComponent>
```

*   `image_file`: Uses a sequence of sprites (`wand_01.png` to `wand_09.png`) for animation.
*   `offset_x`, `offset_y`: Adjusts the sprite's position.

## Particle Emitter Component

Responsible for generating visual effects, such as sparks.

```xml
	<ParticleEmitterComponent 
		emitted_material_name="spark_purple_bright"
		gravity.y="0"
		x_vel_min="0"
		x_vel_max="0"
		y_vel_min="0"
		y_vel_max="0"
		friction="2"
		count_min="1"
		count_max="1"
		lifetime_min="0.3"
		lifetime_max="2.9"
		render_on_grid="1"
		airflow_force="0.85"
		airflow_time="0.101"
		airflow_scale="0.31"
		fade_based_on_lifetime="1"
		create_real_particles="0"
		emit_cosmetic_particles="1"
		emission_interval_min_frames="5"
		emission_interval_max_frames="10"
		is_emitting="1" >
	</ParticleEmitterComponent>
```

*   `emitted_material_name`: Specifies the type of particle to emit (`spark_purple_bright`).
*   `is_emitting`: Controls whether the emitter is active.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Determines the timing of particle emissions.

## Light Component

Adds a light source to the projectile.

```xml
	<LightComponent 
		_enabled="1" 
		radius="150" 
		r="45"
		g="45"
		b="90">
	</LightComponent>
```

*   `radius`: The range of the light.
*   `r`, `g`, `b`: The color of the light.

## Variable Storage Component

Stores a string value, likely used by Lua scripts.

```xml
	<VariableStorageComponent
		name="memory"
		value_string="data/entities/projectiles/enlightened_laser_darkbeam.xml"
		>
	</VariableStorageComponent>
```

*   `name`: The name of the variable (`memory`).
*   `value_string`: The stored string value, pointing to another entity file.

## Lua Components

These components execute custom Lua scripts to add dynamic behavior.

### Wand Behavior Script

```xml
	<LuaComponent
		script_source_file="data/entities/animals/boss_pit/wand.lua"
		execute_every_n_frame="40"
		>
	</LuaComponent>
```

*   `script_source_file`: The path to the primary Lua script for this entity.
*   `execute_every_n_frame`: The script will execute every 40 frames.

### Wand Rotation Script

```xml
	<LuaComponent
		script_source_file="data/entities/animals/boss_pit/wand_rotate.lua"
		execute_every_n_frame="1"
		>
	</LuaComponent>
```

*   `script_source_file`: The path to the Lua script responsible for rotation.
*   `execute_every_n_frame`: The script will execute every frame, likely for smooth rotation.

## Audio Component

Defines the sound effects associated with the projectile.

```xml
	<AudioComponent
		file="data/audio/Desktop/projectiles.bank"
		event_root="projectiles/orb_a" >
	</AudioComponent>
```

*   `file`: The audio bank containing the sound events.
*   `event_root`: The specific sound event to play.