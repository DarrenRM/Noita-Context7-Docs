---
title: Ocarina Projectile (C Note)
category: entities
---

# Ocarina Projectile (C Note)

This document details the configuration for the "C" note projectile fired by the Ocarina in Noita. It defines its physical properties, particle effects, and associated sound.

## Core Entity Configuration

The projectile is based on the default player projectile entity.

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
    <!-- ... other components ... -->
</Entity>
```

### Key Attributes:

*   **`name`**: `$projectile_default` - Inherits base projectile properties.
*   **`tags`**: `projectile_player` - Identifies it as a player-fired projectile.

## Projectile Component

This component governs the projectile's behavior in flight.

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

*   **`lob_min`, `lob_max`**: Controls the arc of the projectile (0.5 to 0.7).
*   **`speed_min`, `speed_max`**: Sets the projectile's speed range (250 to 450).
*   **`lifetime`**: The projectile exists for 2 seconds.
*   **`damage`**: Set to 0, indicating this projectile itself does not deal direct damage.
*   **`on_collision_die`**: Set to 0, meaning it doesn't disappear immediately on hitting a surface.

## Particle Emitters

Two particle emitters are used to create visual effects.

### 1. `ParticleEmitterComponent` (Spark Trail)

This emitter generates white sparks as a trail.

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

### 2. `SpriteParticleEmitterComponent` (Note Glyphs)

This emitter creates sprite-based particles resembling musical notes.

```xml
	<SpriteParticleEmitterComponent
		sprite_file="data/particles/note_$[1-4].xml"
		delay="0"
		lifetime="1.5"
		color.r="1" color.g="0.8" color.b="1" color.a="1"
		color_change.r="0" color_change.g="0" color_change.b="0" color_change.a="-1"
		velocity.x="0" velocity.y="0"
		gravity.x="0" gravity.y="0"
		velocity_slowdown="0"
		rotation="0"
		angular_velocity="0"
		use_velocity_as_rotation="0"
		scale.x="1" scale.y="1"
		scale_velocity.x="0" scale_velocity.y="0"
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

### Key Attributes:

*   **`sprite_file`**: `data/particles/note_$[1-4].xml` - Uses a set of note sprites.
*   **`lifetime`**: Particles last for 1.5 seconds.
*   **`color`**: Initial color is a light pinkish-white.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: Particles are emitted every 4-6 frames.
*   **`randomize_rotation`, `randomize_angular_velocity`, `randomize_velocity`**: Adds slight variations to particle orientation and movement.

## Variable Storage

This component stores a variable to identify the specific ocarina note.

```xml
	<VariableStorageComponent
		name="ocarina_note"
		value_string="c"
		>
	</VariableStorageComponent>
```

### Key Attributes:

*   **`name`**: `ocarina_note` - The identifier for the variable.
*   **`value_string`**: `c` - Specifies this is the "C" note.

## Lua Component

This component links the projectile to a Lua script for its magical effects.

```xml
	<LuaComponent
		script_source_file="data/scripts/magic/ocarina.lua"
		execute_on_added="1"
		remove_after_executed="1"
		>
	</LuaComponent>
```

### Key Attributes:

*   **`script_source_file`**: `data/scripts/magic/ocarina.lua` - The script that handles the ocarina's functionality.
*   **`execute_on_added`**: `1` - The script runs as soon as the projectile is created.
*   **`remove_after_executed`**: `1` - The Lua script component is removed after execution.

## Audio Component

This component defines the sound played when the projectile is fired.

```xml
	<AudioComponent
		file="data/audio/Desktop/projectiles.bank"
		event_root="player_projectiles/ocarina/c"
		set_latest_event_position="1" >
	</AudioComponent>
```

### Key Attributes:

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
*   **`event_root`**: `player_projectiles/ocarina/c` - Specifies the exact sound event for the "C" note ocarina projectile.