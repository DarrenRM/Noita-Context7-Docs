---
title: Orb Laser Emitter Cutter Projectile
category: entities
---

# Orb Laser Emitter Cutter Projectile

This document details the configuration for the "orb_laseremitter_cutter" projectile in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The projectile is based on the `base_projectile.xml` and defines its fundamental properties.

```xml
<Entity 
  name="$projectile_default"
   tags="projectile_player"
   >
```

### Base Projectile Properties

*   **`gravity_y`**: `0` - The projectile is not affected by gravity.
*   **`air_friction`**: `7` - A moderate amount of air friction is applied.
*   **`mass`**: `0.05` - The projectile has a very low mass.

## Projectile Component

This component governs the projectile's behavior in flight and upon collision.

```xml
  <ProjectileComponent 
    _enabled="1" 
	lob_min="0.8"
  	lob_max="1.0"
  	speed_min="40"
  	speed_max="40"
    die_on_low_velocity="0"
    on_death_explode="0"
    on_death_gfx_leave_sprite="0" 
    on_lifetime_out_explode="0"
	explosion_dont_damage_shooter="1"
    damage="0.8"
    on_collision_die="0"
    lifetime="60" 
	knockback_force="1.3"
	>
  </ProjectileComponent>
```

*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Controls the projectile's lobbing behavior, indicating a very straight trajectory.
*   **`speed_min` / `speed_max`**: `40` - The projectile travels at a constant speed of 40.
*   **`die_on_low_velocity`**: `0` - The projectile does not die when its velocity becomes low.
*   **`on_death_explode`**: `0` - The projectile does not explode upon death.
*   **`on_lifetime_out_explode`**: `0` - The projectile does not explode when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - If an explosion were to occur, it would not damage the shooter.
*   **`damage`**: `0.8` - The base damage dealt by the projectile.
*   **`on_collision_die`**: `0` - The projectile does not die upon collision.
*   **`lifetime`**: `60` - The projectile exists for 60 frames.
*   **`knockback_force`**: `1.3` - The force applied to knock back entities upon collision.

## Sprite Component

Defines the visual representation of the projectile.

```xml
  <SpriteComponent 
    _enabled="0" 
    alpha="1" 
    image_file="data/projectiles_gfx/orb_green.xml" 
    next_rect_animation="" 
    offset_x="6" 
    offset_y="6" 
    rect_animation="spawn" 
	emissive="1"
    additive="1"
     
	update_transform_rotation="0"
	>
  </SpriteComponent>
```

*   **`_enabled`**: `0` - This sprite is disabled by default, suggesting it might be controlled by other components or scripts.
*   **`image_file`**: `data/projectiles_gfx/orb_green.xml` - Specifies the graphical asset used.
*   **`emissive`**: `1` - The sprite emits light.
*   **`additive`**: `1` - The sprite uses additive blending for its rendering.

## Particle Emitter Component

Manages the emission of cosmetic particles.

```xml
	<ParticleEmitterComponent 
		emitted_material_name="spark_green"
		gravity.y="0.10"
		offset.x="0"
		offset.y="0"
		x_pos_offset_min="-1"
		y_pos_offset_min="-1"
		x_pos_offset_max="1"
		y_pos_offset_max="1"
		x_vel_min="-4"
		x_vel_max="4"
		y_vel_min="-4"
		y_vel_max="4"
		count_min="1"
		count_max="5"
		lifetime_min="0.6"
		lifetime_max="0.8"
		render_on_grid="1"
		airflow_force="0.1"
		airflow_time="0.101"
		airflow_scale="2.01"
		fade_based_on_lifetime="1"
		create_real_particles="0"
		emit_cosmetic_particles="1"
		emission_interval_min_frames="0"
		emission_interval_max_frames="1"
		is_emitting="1" >
    </ParticleEmitterComponent>
```

*   **`emitted_material_name`**: `spark_green` - The type of particle emitted.
*   **`gravity.y`**: `0.10` - Particles have a slight downward gravity.
*   **`count_min` / `count_max`**: `1` / `5` - The number of particles emitted per interval.
*   **`lifetime_min` / `lifetime_max`**: `0.6` / `0.8` - The lifespan of emitted particles.
*   **`emit_cosmetic_particles`**: `1` - Ensures cosmetic particles are emitted.
*   **`is_emitting`**: `1` - The emitter is active.

## Light Component

Adds a light source to the projectile.

```xml
  <LightComponent 
    _enabled="1" 
    radius="150" 
    r="30"
    g="90"
    b="30">
  </LightComponent>
```

*   **`_enabled`**: `1` - The light component is active.
*   **`radius`**: `150` - The radius of the light emitted.
*   **`r`, `g`, `b`**: `30`, `90`, `30` - Defines the greenish color of the light.

## Audio Component

Specifies the sound effects associated with the projectile.

```xml
	<AudioComponent
		file="data/audio/Desktop/projectiles.bank"
		event_root="projectiles/orb_b" >
	</AudioComponent>
```

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank file.
*   **`event_root`**: `projectiles/orb_b` - The root event for projectile sounds.

## Laser Emitter Component

This component enables the projectile to emit a laser beam.

```xml
	<LaserEmitterComponent
		is_emitting="0"
		>
		<laser
			damage_to_entities="0.09"
			max_cell_durability_to_destroy="14"
			damage_to_cells="100000"
			root_entity_is_responsible_for_damage="1"
			max_length="64"
			beam_radius="2.5"
			hit_particle_chance="40"
			beam_particle_chance="90"
			beam_particle_type="spark_green"
			>
		</laser>
	</LaserEmitterComponent>
```

*   **`is_emitting`**: `0` - The laser is initially not emitting, likely controlled by a script.
*   **`laser.damage_to_entities`**: `0.09` - The damage dealt to entities by the laser beam.
*   **`laser.max_cell_durability_to_destroy`**: `14` - The maximum durability of cells the laser can destroy.
*   **`laser.damage_to_cells`**: `100000` - High damage to cells, indicating it can cut through terrain.
*   **`laser.root_entity_is_responsible_for_damage`**: `1` - The projectile entity is responsible for damage calculations.
*   **`laser.max_length`**: `64` - The maximum length of the laser beam.
*   **`laser.beam_radius`**: `2.5` - The radius of the laser beam.
*   **`laser.hit_particle_chance`**: `40` - The chance to spawn particles on hit.
*   **`laser.beam_particle_chance`**: `90` - The chance to spawn particles along the beam.
*   **`laser.beam_particle_type`**: `spark_green` - The type of particles emitted along the beam.

## Lua Component

This component executes a Lua script to manage the laser emitter's behavior.

```xml
	<LuaComponent
		script_source_file="data/scripts/projectiles/laser_emitter_start.lua"
		execute_every_n_frame="2"
		remove_after_executed="1"
		>
	</LuaComponent>
```

*   **`script_source_file`**: `data/scripts/projectiles/laser_emitter_start.lua` - The script responsible for initiating the laser emission.
*   **`execute_every_n_frame`**: `2` - The script executes every 2 frames.
*   **`remove_after_executed`**: `1` - The Lua component is removed after its initial execution.

## Variable Storage Component

Stores a variable related to the projectile's file path.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/deck/orb_laseremitter_cutter.xml"
		>
	</VariableStorageComponent>
```

*   **`name`**: `projectile_file` - The name of the stored variable.
*   **`value_string`**: `data/entities/projectiles/deck/orb_laseremitter_cutter.xml` - The value of the variable, pointing to the projectile's own XML file.