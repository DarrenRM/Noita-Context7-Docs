---
title: Kantele Projectile (D)
category: entities
---

# Kantele Projectile (D)

This document details the configuration for the "D" note projectile fired by the Kantele wand in Noita.

## Entity Definition

The core entity is a player projectile with specific properties related to its flight and impact.

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

*   **`name="$projectile_default"`**: Standard projectile name.
*   **`tags="projectile_player"`**: Identifies this as a projectile originating from the player.
*   **`gravity_y="0"`**: The projectile is not affected by gravity.
*   **`air_friction="8"`**: Moderate air resistance.
*   **`mass="0.01"`**: Very light projectile.

## Projectile Component

This component governs the projectile's behavior in flight and upon collision.

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

*   **`lob_min="0.5"`, `lob_max="0.7"`**: Controls the arc of the projectile, giving it a slight upward trajectory.
*   **`speed_min="250"`, `speed_max="450"`**: Defines the projectile's initial velocity range.
*   **`direction_random_rad="0.00"`**: No randomness in the initial firing direction.
*   **`lifetime="2"`**: The projectile exists for 2 seconds.
*   **`damage="0"`**: This projectile itself does not deal direct damage.
*   **`on_collision_die="0"`**: The projectile does not disappear upon hitting an entity.

## Particle Emitters

Two particle emitters are used to create visual effects for the projectile.

### 1. Spark Emitter

This emitter generates white sparks.

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

### 2. Sprite Particle Emitter (Notes)

This emitter creates "note" sprites as visual flair.

```xml
	<SpriteParticleEmitterComponent
		sprite_file="data/particles/note_$[1-4].xml"
		delay="0"
		lifetime="1.5"
		color.r="1" color.g="1" color.b="0.8" color.a="1"
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

*   **`sprite_file="data/particles/note_$[1-4].xml"`**: Uses a set of note sprites.
*   **`lifetime="1.5"`**: Note sprites last for 1.5 seconds.
*   **`color.r="1" color.g="1" color.b="0.8" color.a="1"`**: Yellowish-white color.
*   **`emission_interval_min_frames="4"`, `emission_interval_max_frames="6"`**: Notes are emitted periodically.
*   **`randomize_rotation`**, **`randomize_angular_velocity`**, **`randomize_velocity`**: Adds slight variations to the notes' movement and orientation.

## Variable Storage

This component stores a string value indicating which note this projectile represents.

```xml
	<VariableStorageComponent
		name="kantele_note"
		value_string="d"
		>
	</VariableStorageComponent>
```

### Key Attributes:

*   **`name="kantele_note"`**: The name of the variable.
*   **`value_string="d"`**: The value, identifying this as the "D" note.

## Lua Component

This component links the projectile to a Lua script for custom behavior.

```xml
	<LuaComponent
		script_source_file="data/scripts/magic/kantele.lua"
		execute_on_added="1"
		remove_after_executed="1"
		>
	</LuaComponent>
```

### Key Attributes:

*   **`script_source_file="data/scripts/magic/kantele.lua"`**: The script responsible for the projectile's effects.
*   **`execute_on_added="1"`**: The script runs as soon as the projectile is created.
*   **`remove_after_executed="1"`**: The Lua script is removed after its initial execution.

## Audio Component

This component defines the sound played when the projectile is fired.

```xml
	<AudioComponent
		file="data/audio/Desktop/projectiles.bank"
		event_root="player_projectiles/kantele/d"
		set_latest_event_position="1" >
	</AudioComponent>
```

### Key Attributes:

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank containing the sound.
*   **`event_root="player_projectiles/kantele/d"`**: Specifies the exact sound event for the Kantele's "D" note projectile.