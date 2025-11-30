---
title: Orb Projectile
category: entities
---

# Orb Projectile

This document details the configuration for a standard "orb" projectile entity in Noita, focusing on its core attributes for AI-assisted modding.

## Core Entity Configuration

The projectile is defined as an `Entity` with a base projectile configuration.

```xml
<Entity
	name="$projectile_default"
	>

	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
			gravity_y="0"
			air_friction="0"
			mass="0.05"
			>
		</VelocityComponent>
	</Base>
```

### Key Attributes:

*   **`name`**: `$projectile_default` - A generic name, often overridden by specific projectile types.
*   **`Base file`**: `data/entities/base_projectile.xml` - Inherits fundamental projectile properties.
*   **`VelocityComponent`**:
    *   `gravity_y="0"`: No gravity applied.
    *   `air_friction="0"`: No air resistance.
    *   `mass="0.05"`: Low mass.

## Projectile Component

This component defines the projectile's behavior, including its trajectory, damage, and death effects.

```xml
	<ProjectileComponent
		_enabled="1"
		lob_min="0.8"
		lob_max="1.0"
		speed_min="350"
		speed_max="350"
		die_on_low_velocity="0"
		on_death_explode="1"
		on_death_gfx_leave_sprite="0"
		on_lifetime_out_explode="1"
		explosion_dont_damage_shooter="1"
		damage="0.8"
		on_collision_die="1"
		lifetime="200"
		knockback_force="1.0"
		>
		<config_explosion
			never_cache="1"
			camera_shake="0"
			explosion_radius="6"
			explosion_sprite="data/particles/explosion_016_plasma.xml"
			explosion_sprite_lifetime="0.0"
			create_cell_probability="0"
			ray_energy="5000"
			hole_destroy_liquid="1"
			hole_enabled="1"
			hole_image="data/temp/explosion_hole.png"
			explosion_sprite_emissive="1"
			explosion_sprite_additive="1"
			particle_effect="0"
			damage_mortals="0"
			physics_explosion_power.min="0.3"
			physics_explosion_power.max="0.4"
			physics_throw_enabled="1"
			shake_vegetation="1"
			sparks_enabled="0"
			light_fade_time="0.8"
			light_r="15"
			light_g="15"
			light_b="40"
			stains_enabled="0"
			audio_enabled="0" >
		</config_explosion>
	</ProjectileComponent>
```

### Key Attributes:

*   **`lob_min`, `lob_max`**: `0.8` to `1.0` - Controls the arc of the projectile.
*   **`speed_min`, `speed_max`**: `350` - Constant projectile speed.
*   **`die_on_low_velocity`**: `0` - Does not die if velocity drops below a threshold.
*   **`on_death_explode`**: `1` - Explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - Explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - The explosion does not harm the entity that fired it.
*   **`damage`**: `0.8` - Base damage dealt by the projectile.
*   **`on_collision_die`**: `1` - Dies upon colliding with something.
*   **`lifetime`**: `200` - Duration in frames before expiring.
*   **`knockback_force`**: `1.0` - The force applied to knock back entities.
*   **`config_explosion`**: Defines the properties of the explosion upon death.
    *   `explosion_radius`: `6`
    *   `explosion_sprite`: `data/particles/explosion_016_plasma.xml`
    *   `ray_energy`: `5000`
    *   `hole_enabled`: `1`
    *   `physics_explosion_power.min`, `.max`: `0.3` to `0.4`
    *   `light_r`, `g`, `b`: `15`, `15`, `40` (a bluish light)

## Visual Components

### Sprite Components

Two `SpriteComponent`s are used to render the projectile.

```xml
	<SpriteComponent
		_enabled="1"
		alpha="1"
		image_file="data/projectiles_gfx/orb_blue.xml"
		offset_x="6"
		offset_y="6"
		rect_animation="spawn"
		update_transform_rotation="0"
		>
	</SpriteComponent>

	<SpriteComponent
		_enabled="1"
		alpha="1"
		image_file="data/projectiles_gfx/orb_blue.xml"
		offset_x="6"
		offset_y="6"
		rect_animation="spawn"
		emissive="1"
		additive="1"
		update_transform_rotation="0"
		>
	</SpriteComponent>
```

*   **`image_file`**: `data/projectiles_gfx/orb_blue.xml` - Specifies the sprite sheet.
*   **`offset_x`, `offset_y`**: `6` - Offsets the sprite's position.
*   **`rect_animation`**: `spawn` - Uses a specific animation from the sprite sheet.
*   The second sprite component has `emissive="1"` and `additive="1"` for a glowing effect.

### Particle Emitter Component

This component generates cosmetic particles.

```xml
	<ParticleEmitterComponent
		emitted_material_name="spark_blue"
		gravity.y="0"
		offset.x="-0.5"
		offset.y="0.5"
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

*   **`emitted_material_name`**: `spark_blue` - The type of particle emitted.
*   **`emit_cosmetic_particles`**: `1` - Ensures these are visual effects, not physical entities.
*   **`is_emitting`**: `1` - The emitter is active.

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

*   **`radius`**: `150` - The range of the light.
*   **`r`, `g`, `b`**: `45`, `45`, `90` - Defines the light color (bluish).

## Audio Component

Defines the sound effects associated with the projectile.

```xml
	<AudioComponent
		file="data/audio/Desktop/projectiles.bank"
		event_root="projectiles/orb_a" >
	</AudioComponent>
```

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sounds.
*   **`event_root`**: `projectiles/orb_a` - The specific sound event to trigger.

## Variable Storage Component

Stores a reference to the projectile's own entity file.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/orb.xml"
		>
	</VariableStorageComponent>
```

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/orb.xml` - The value, pointing to this entity's file.