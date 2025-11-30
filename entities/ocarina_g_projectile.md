---
title: Ocarina G# Projectile
category: entities
---

# Ocarina G# Projectile

This document describes the `ocarina_gsharp.xml` entity, which defines the G# projectile fired by the Ocarina.

## Core Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="8"`: Moderate air resistance.
    *   `mass="0.01"`: Very light projectile.

### Projectile Properties (`ProjectileComponent`)

This component defines the specific behavior and characteristics of the G# projectile.

*   **`_enabled="1"`**: The component is active.
*   **`lob_min="0.5"`, `lob_max="0.7"`**: Controls the arc of the projectile.
*   **`speed_min="250"`, `speed_max="450"`**: Defines the projectile's speed range.
*   **`lifetime="2"`**: The projectile exists for 2 seconds.
*   **`damage="0"`**: This projectile does not deal direct damage.
*   **`on_collision_die="0"`**: The projectile does not die upon collision.
*   **`lifetime_randomness="0"`**: The projectile's lifetime is fixed.

### Particle Emitters

#### `ParticleEmitterComponent` (Spark Trail)

This component generates white sparks as a visual trail.

*   **`emitted_material_name="spark_white"`**: The material used for the sparks.
*   **`count_min="8"`, `count_max="10"`**: The number of sparks emitted per interval.
*   **`lifetime_min="0.2"`, `lifetime_max="1.2"`**: The duration sparks remain visible.
*   **`airflow_force="1.5"`, `airflow_time="1.101"`, `airflow_scale="0.05"`**: Influences how sparks react to airflow.

#### `SpriteParticleEmitterComponent` (Note Visuals)

This component emits sprite particles resembling musical notes.

*   **`sprite_file="data/particles/note_$[1-4].xml"`**: Uses a set of note sprites.
*   **`lifetime="1.5"`**: The duration these note sprites are visible.
*   **`color.r="1" color.g="1" color.b="0.6" color.a="1"`**: Initial yellow-ish color.
*   **`color_change.a="-1"`**: The alpha (transparency) decreases over time.
*   **`emission_interval_min_frames="4"`, `emission_interval_max_frames="6"`**: Controls the rate of note sprite emission.
*   **`randomize_rotation`**: Adds slight random rotation to the notes.
*   **`randomize_angular_velocity`**: Adds slight random spinning to the notes.

### Variable Storage (`VariableStorageComponent`)

*   **`name="ocarina_note"`**: Stores the note type.
*   **`value_string="gsharp"`**: Identifies this projectile as the G# note.

### Lua Script (`LuaComponent`)

*   **`script_source_file="data/scripts/magic/ocarina.lua"`**: Links to the script that handles the Ocarina's functionality.
*   **`execute_on_added="1"`**: The script runs when the projectile is created.
*   **`remove_after_executed="1"`**: The Lua component is removed after execution.

### Audio (`AudioComponent`)

*   **`event_root="player_projectiles/ocarina/gsharp"`**: Specifies the sound event for this projectile.

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
	
	<SpriteParticleEmitterComponent
		sprite_file="data/particles/note_$[1-4].xml"
		delay="0"
		lifetime="1.5"
		color.r="1" color.g="1" color.b="0.6" color.a="1"
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
	
	<VariableStorageComponent
		name="ocarina_note"
		value_string="gsharp"
		>
	</VariableStorageComponent>
	
	<LuaComponent
		script_source_file="data/scripts/magic/ocarina.lua"
		execute_on_added="1"
		remove_after_executed="1"
		>
	</LuaComponent>

	<AudioComponent
		file="data/audio/Desktop/projectiles.bank"
		event_root="player_projectiles/ocarina/gsharp"
		set_latest_event_position="1" >
	</AudioComponent>

</Entity>
```