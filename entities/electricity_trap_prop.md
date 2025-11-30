---
title: Electricity Trap Prop
category: entities
---

# Electricity Trap Prop

This entity represents a physics-based trap that activates when it receives electricity. It deals damage and creates an electrical explosion upon destruction.

## Key Components

### PhysicsBody2Component
Manages the physical properties of the trap.
- `allow_sleep`: Whether the body can go to sleep when inactive.
- `angular_damping`: Resistance to angular motion.
- `linear_damping`: Resistance to linear motion.

### PhysicsImageShapeComponent
Defines the visual shape and physical material of the trap.
- `image_file`: Path to the sprite used for the trap.
- `material`: The physical material of the trap (e.g., "steel").

### ElectricityReceiverComponent
Enables the entity to receive and react to electricity.
- `radius`: The radius around the trap that can receive electrical signals.
- `active_time_frames`: How long the trap remains active after receiving a signal.

### LuaComponent
Attaches a Lua script to the entity for custom behavior.
- `script_source_file`: Path to the Lua script that handles the trap's logic.
- `execute_every_n_frame`: How often the script is executed.

### SpriteParticleEmitterComponent
Responsible for emitting visual particles, specifically sparks.
- `sprite_file`: The particle sprite to use.
- `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the timing of particle emissions.
- `count_min`, `count_max`: The number of particles emitted per interval.
- `randomize_position`: Defines the area where particles can spawn.

### ParticleEmitterComponent
Another particle emitter, likely for different types of visual effects.
- `emitted_material_name`: The material name of the particles to emit.
- `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Velocity range for emitted particles.
- `count_min`, `count_max`: Number of particles emitted.
- `lifetime_min`, `lifetime_max`: Duration particles exist.
- `emission_interval_min_frames`, `emission_interval_max_frames`: Timing of emissions.
- `is_emitting`: Whether the emitter is active.

### DamageModelComponent
Handles how the entity takes damage and its properties related to damage.
- `hp`: The hit points of the trap.
- `materials_that_damage`: List of materials that can damage this entity.
- `materials_how_much_damage`: The amount of damage dealt by each material.
- `damage_multipliers`: Modifiers for different damage types.
    - `melee`: Multiplier for melee damage.
    - `electricity`: Multiplier for electrical damage.

### ExplodeOnDamageComponent
Defines the explosion behavior when the entity is damaged or destroyed.
- `explode_on_death_percent`: Probability of exploding when health reaches 0.
- `physics_body_destruction_required`: Threshold for physics body destruction to trigger explosion.
- `config_explosion`: Configuration for the explosion effect.
    - `damage`: Damage dealt by the explosion.
    - `camera_shake`: Intensity of camera shake.
    - `explosion_radius`: The radius of the explosion.
    - `explosion_sprite`: The visual effect for the explosion.
    - `load_this_entity`: An entity to spawn upon explosion (e.g., "thunderball.xml").
    - `ray_energy`: Energy of the electrical discharge.
    - `physics_explosion_power`: Force of the physics-based explosion.
    - `audio_event_name`: The sound effect to play for the explosion.

```xml
<Entity tags="mortal,hittable,teleportable_NOT,prop,prop_physics">

	<PhysicsBody2Component 
		allow_sleep="1"
		angular_damping="0"
		linear_damping="0" 
	></PhysicsBody2Component>

	<PhysicsImageShapeComponent 
		is_root="1"
		centered="1" 
		image_file="data/props_gfx/trap_electricity.png"
		material="steel"
	></PhysicsImageShapeComponent>

	<ElectricityReceiverComponent
		radius="6"
		active_time_frames="100"
	></ElectricityReceiverComponent>

	<LuaComponent
		_tags="electricity_effect"
		script_source_file="data/scripts/props/physics_trap_electricity_pulse.lua"
		execute_every_n_frame="128"
	></LuaComponent>

	<SpriteParticleEmitterComponent
		_tags="particles_a"
		_enabled="0"
		sprite_file="data/particles/spark_electric.xml"
		delay="0"
		lifetime="0"
		color.r="1.0" color.g="1" color.b="1" color.a="1"
		color_change.r="0" color_change.g="0" color_change.b="0" color_change.a="0"
		velocity.x="0" velocity.y="0"
		gravity.x="0" gravity.y="10"
		velocity_slowdown="0"
		rotation="0"
		angular_velocity="0"
		use_velocity_as_rotation="0"
		scale.x="1" scale.y="1"
		scale_velocity.x="0" scale_velocity.y="0"
		emission_interval_min_frames="128"
		emission_interval_max_frames="128"
		count_min="3" count_max="10"
		randomize_rotation.min="-3.1415"
		randomize_rotation.max="3.1415"
		randomize_position.min_x="-14"
		randomize_position.max_x="14"
		randomize_position.min_y="-14"
		randomize_position.max_y="14"
	></SpriteParticleEmitterComponent>

	<ParticleEmitterComponent 
	    _tags="particles_b"
	    _enabled="0"
	    emitted_material_name="spark_electric"
	    offset.x="0"
	    offset.y="0"
	    x_pos_offset_min="-4"
	    x_pos_offset_max="4"
	    y_pos_offset_min="-4"
	    y_pos_offset_max="4"
	    x_vel_min="-50"
	    x_vel_max="50"
	    y_vel_min="-100"
	    y_vel_max="50"
	    count_min="20"
	    count_max="60"
	    lifetime_min="0.1"
	    lifetime_max="0.75"
	    create_real_particles="0"
	    emit_cosmetic_particles="1"
	    collide_with_grid="0"
	    emission_interval_min_frames="128"
	    emission_interval_max_frames="128"
	    is_emitting="1"
	    fade_based_on_lifetime="0"
	    draw_as_long="1"
	></ParticleEmitterComponent>

	<DamageModelComponent 
		air_needed="0" 
		blood_material="spark_electric" 
		blood_multiplier="3"
		drop_items_on_death="0" 
		falling_damage_damage_max="1.2" 
		falling_damage_damage_min="0.1" 
		falling_damage_height_max="250" 
		falling_damage_height_min="70" 
		falling_damages="0" 
		fire_damage_amount="0.4" 
		fire_probability_of_ignition="0"
		critical_damage_resistance="1"
		hp="30" 
		is_on_fire="0" 
		materials_create_messages="0" 
		materials_damage="1" 
		materials_that_damage="fire,lava,acid"
		materials_how_much_damage="0.0002,0.0001,0.001"
		ragdoll_filenames_file="" 
		ragdoll_material="" 
		><damage_multipliers
			melee="0.1"
			electricity="0"
		></damage_multipliers>
	</DamageModelComponent>

	<ExplodeOnDamageComponent
		explode_on_death_percent="1"
		explode_on_damage_percent="0.0"
		physics_body_modified_death_probability="1.0" 
		physics_body_destruction_required="0.15"
		><config_explosion
			never_cache="0"
			damage="2.6"
			camera_shake="10" 
			explosion_radius="16" 
			explosion_sprite="data/particles/explosion_016_electric.xml" 
			explosion_sprite_lifetime="10" 
			create_cell_probability="50" 
			hole_destroy_liquid="0" 
			load_this_entity="data/entities/projectiles/thunderball.xml"
			hole_enabled="1" 
			ray_energy="25000"
			particle_effect="1" 
			damage_mortals="1" 
			physics_explosion_power.min="1.7" 
			physics_explosion_power.max="2.3" 
			physics_throw_enabled="1"
			shake_vegetation="1" 
			sparks_count_max="20" 
			sparks_count_min="7" 
			sparks_enabled="1" 
			stains_enabled="1" 
			stains_radius="15" 
			delay.min="1"
			delay.max="4"
			explosion_delay_id="1"
			audio_event_name="explosions/electric"
		></config_explosion>
	</ExplodeOnDamageComponent>

</Entity>
```