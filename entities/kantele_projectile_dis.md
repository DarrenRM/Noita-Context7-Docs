---
title: Kantele Projectile (Dis)
category: entities
---

# Kantele Projectile (Dis)

This document describes the "Dis" variant of the Kantele projectile in Noita, focusing on its key attributes for AI-assisted modding.

## Entity Definition

The core entity definition for this projectile.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
			gravity_y="0"
			air_friction="8"
			mass="0.01"
		>
		</VelocityComponent>
	</Base>
    ...
</Entity>
```

### Key Attributes:

*   **`name`**: `$projectile_default` - Indicates this entity uses the default projectile base.
*   **`tags`**: `projectile_player` - Identifies this as a projectile fired by the player.

## Projectile Component

Defines the projectile's behavior and physical properties.

```xml
	<ProjectileComponent
		_enabled="1"
		lob_min="0.5"
		lob_max="0.7"
		speed_min="250"
		speed_max="450"
		direction_random_rad="0.00"
		on_death_explode="0"
		on_death_gfx_leave_sprite="0"
		on_lifetime_out_explode="0"
		explosion_dont_damage_shooter="0"
		on_collision_die="0"
		lifetime="2"
		damage="0"
		velocity_sets_scale="0"
		lifetime_randomness="0"
		ragdoll_force_multiplier="0.001"
		hit_particle_force_multiplier="0.001"
		knockback_force="0"
		physics_impulse_coeff="0"
		>
	</ProjectileComponent>
```

### Key Attributes:

*   **`lob_min`, `lob_max`**: Controls the minimum and maximum arc of the projectile.
*   **`speed_min`, `speed_max`**: Defines the range of projectile speeds.
*   **`lifetime`**: The duration (in seconds) the projectile exists before expiring.
*   **`damage`**: The amount of damage this projectile deals (set to 0 here, likely handled by Lua).
*   **`on_collision_die`**: If `0`, the projectile does not die upon collision.

## Particle Emitters

These components define the visual effects associated with the projectile.

### `ParticleEmitterComponent` (Standard Particles)

```xml
	<ParticleEmitterComponent
		emitted_material_name="spark_white"
		offset.x="0"
		offset.y="0"
		x_pos_offset_min="-2"
		x_pos_offset_max="2"
		y_pos_offset_min="-2"
		y_pos_offset_max="2"
		x_vel_min="0"
		x_vel_max="80"
		y_vel_min="-10"
		y_vel_max="10"
		gravity.y="0.0"
		count_min="8"
		count_max="10"
		lifetime_min="0.2"
		lifetime_max="1.2"
		is_trail="0"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		airflow_force="1.5"
		airflow_time="1.101"
		airflow_scale="0.05"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		emit_cosmetic_particles="1"
		create_real_particles="0"
		is_emitting="1" >
	</ParticleEmitterComponent>
```

#### Key Attributes:

*   **`emitted_material_name`**: `spark_white` - The material used for the emitted particles.
*   **`count_min`, `count_max`**: Number of particles emitted per interval.
*   **`lifetime_min`, `lifetime_max`**: Duration of individual particles.
*   **`airflow_force`, `airflow_time`, `airflow_scale`**: Parameters controlling how airflow affects particles.

### `SpriteParticleEmitterComponent` (Cosmetic Notes)

This emitter creates sprite-based particles, likely representing musical notes.

```xml
	<SpriteParticleEmitterComponent
		sprite_file="data/particles/note_$[1-4].xml"
		delay="0"
		lifetime="1.5"
		color.r="1" color.g="0.6" color.b="1" color.a="1"
		color_change.r="0" color_change.g="0" color_change.b="0" color_change.a="-1"
		velocity.x="0" velocity.y="0"
		gravity.x="0" gravity.y="0"
		rotation="0"
		angular_velocity="0"
		scale.x="1" scale.y="1"
		emission_interval_min_frames="4"
		emission_interval_max_frames="6"
		count_min="1" count_max="1"
		randomize_rotation.min="-0.3415"
		randomize_rotation.max="0.3415"
		randomize_angular_velocity.min="-0.1415"
		randomize_angular_velocity.max="0.1415"
		randomize_velocity.min_x="-5"
		randomize_velocity.max_x="5"
		randomize_velocity.min_y="-5"
		randomize_velocity.max_y="5"
		entity_velocity_multiplier="0.1"
	>
	</SpriteParticleEmitterComponent>
```

#### Key Attributes:

*   **`sprite_file`**: `data/particles/note_$[1-4].xml` - Specifies the sprite files for the particles (likely variations of a musical note).
*   **`lifetime`**: Duration of these sprite particles.
*   **`color`**: Initial color of the particles (pinkish hue).
*   **`color_change`**: How the color changes over time (alpha decreases).
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: Controls the rate of emission.
*   **`randomize_rotation`, `randomize_angular_velocity`, `randomize_velocity`**: Adds variation to the movement and orientation of the particles.

## Variable Storage Component

Stores custom variables associated with the entity.

```xml
	<VariableStorageComponent
		name="kantele_note"
		value_string="dis"
		>
	</VariableStorageComponent>
```

### Key Attributes:

*   **`name`**: `kantele_note` - The name of the variable.
*   **`value_string`**: `dis` - The value assigned to the variable, identifying this specific Kantele note.

## Lua Component

Links the entity to a Lua script for custom logic.

```xml
	<LuaComponent
		script_source_file="data/scripts/magic/kantele.lua"
		execute_on_added="1"
		remove_after_executed="1"
		>
	</LuaComponent>
```

### Key Attributes:

*   **`script_source_file`**: `data/scripts/magic/kantele.lua` - The Lua script that handles the projectile's logic.
*   **`execute_on_added`**: `1` - The script executes when the entity is added to the game world.
*   **`remove_after_executed`**: `1` - The Lua component is removed after its script has run once.

## Audio Component

Defines the sound effects associated with the projectile.

```xml
	<AudioComponent
		file="data/audio/Desktop/projectiles.bank"
		event_root="player_projectiles/kantele/dis"
		set_latest_event_position="1" >
	</AudioComponent>
```

### Key Attributes:

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
*   **`event_root`**: `player_projectiles/kantele/dis` - The specific sound event to trigger.
*   **`set_latest_event_position`**: `1` - Ensures the sound plays at the projectile's current position.