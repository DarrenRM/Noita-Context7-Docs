---
title: Weak Orb Laser Emitter Projectile
category: entities
---

# Weak Orb Laser Emitter Projectile

This document details the configuration for the "Weak Orb Laser Emitter" projectile in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The projectile is defined as an `Entity` with the following primary attributes:

*   **`name`**: `$projectile_default` - Inherits default projectile properties.
*   **`tags`**: `projectile_player` - Identifies this projectile as originating from the player.

## Base Projectile Properties

Inherits from `data/entities/base_projectile.xml`.

### `Base.VelocityComponent`

Controls the projectile's movement physics.

*   **`gravity_y`**: `0` - No vertical gravity applied.
*   **`air_friction`**: `7` - Moderate air resistance.
*   **`mass`**: `0.05` - Low mass, contributing to its speed.

## Projectile Component (`ProjectileComponent`)

Defines the specific behaviors and characteristics of this projectile.

*   **`_enabled`**: `1` - Component is active.
*   **`lob_min`**: `0.8` - Minimum lobbing factor.
*   **`lob_max`**: `1.0` - Maximum lobbing factor.
*   **`speed_min`**: `40` - Minimum projectile speed.
*   **`speed_max`**: `40` - Maximum projectile speed.
*   **`die_on_low_velocity`**: `0` - Projectile does not die if its velocity drops too low.
*   **`on_death_explode`**: `0` - No explosion upon death.
*   **`on_death_gfx_leave_sprite`**: `0` - No sprite left behind on death.
*   **`on_lifetime_out_explode`**: `0` - No explosion when lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - If an explosion were to occur, it wouldn't damage the shooter.
*   **`damage`**: `0.8` - Base damage dealt by the projectile itself (distinct from laser damage).
*   **`on_collision_die`**: `0` - Projectile does not die upon collision.
*   **`lifetime`**: `100` - Duration in frames before the projectile is removed.
*   **`knockback_force`**: `1.3` - Force applied to entities upon collision.

## Visuals (`SpriteComponent`)

Defines the projectile's appearance.

*   **`_enabled`**: `0` - This sprite is disabled by default, likely controlled by other components or scripts.
*   **`alpha`**: `1` - Fully opaque.
*   **`image_file`**: `data/projectiles_gfx/orb_blue.xml` - Specifies the graphical asset.
*   **`offset_x`**: `6` - Horizontal offset for the sprite.
*   **`offset_y`**: `6` - Vertical offset for the sprite.
*   **`rect_animation`**: `spawn` - Uses the "spawn" animation from the sprite sheet.
*   **`emissive`**: `1` - The sprite emits light.
*   **`additive`**: `1` - Uses additive blending for the sprite.
*   **`update_transform_rotation`**: `0` - Sprite rotation is not updated based on projectile movement.

## Particle Effects (`ParticleEmitterComponent`)

Generates visual particle effects.

*   **`emitted_material_name`**: `spark_blue` - The type of particle to emit.
*   **`gravity.y`**: `0.10` - Slight downward gravity for particles.
*   **`x_pos_offset_min` / `max`**: `-1` / `1` - Horizontal position variation.
*   **`y_pos_offset_min` / `max`**: `-1` / `1` - Vertical position variation.
*   **`x_vel_min` / `max`**: `-4` / `4` - Horizontal velocity range.
*   **`y_vel_min` / `max`**: `-4` / `4` - Vertical velocity range.
*   **`count_min` / `max`**: `1` / `5` - Number of particles emitted per burst.
*   **`lifetime_min` / `max`**: `0.6` / `0.8` - Particle lifespan in seconds.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`airflow_force`**: `0.1` - Affects particle movement with airflow.
*   **`airflow_time`**: `0.101` - Duration of airflow effect.
*   **`airflow_scale`**: `2.01` - Intensity of airflow effect.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime ends.
*   **`create_real_particles`**: `0` - Does not create actual physics-simulated particles.
*   **`emit_cosmetic_particles`**: `1` - Emits purely visual particles.
*   **`emission_interval_min_frames` / `max_frames`**: `0` / `1` - Particles are emitted continuously or in rapid succession.
*   **`is_emitting`**: `1` - The emitter is active.

## Lighting (`LightComponent`)

Adds a light source to the projectile.

*   **`_enabled`**: `1` - Light component is active.
*   **`radius`**: `150` - The radius of the light effect.
*   **`r`, `g`, `b`**: `30`, `30`, `90` - Defines the light color as a dark blue.

## Audio (`AudioComponent`)

Manages sound effects for the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank file.
*   **`event_root`**: `projectiles/orb_b` - The root event for projectile sounds.

## Laser Emitter (`LaserEmitterComponent`)

Configures the laser beam functionality.

*   **`is_emitting`**: `0` - The laser is not emitting by default; it's likely triggered by a script.

### `LaserEmitterComponent.laser`

Specific parameters for the laser beam.

*   **`damage_to_entities`**: `0.065` - Damage dealt to entities per second by the laser.
*   **`max_cell_durability_to_destroy`**: `11` - How much durability a cell needs to be destroyed by the laser.
*   **`damage_to_cells`**: `10000` - High damage to terrain cells.
*   **`root_entity_is_responsible_for_damage`**: `1` - The entity itself handles damage calculations.
*   **`max_length`**: `96` - The maximum length of the laser beam.
*   **`beam_radius`**: `2.0` - The width of the laser beam.
*   **`hit_particle_chance`**: `20` - Chance to spawn particles on hit.
*   **`beam_particle_chance`**: `90` - Chance to spawn particles along the beam.
*   **`beam_particle_type`**: `plasma_fading` - The type of particles to spawn along the beam.

## Scripting (`LuaComponent`)

Attaches Lua scripts to control behavior.

*   **`script_source_file`**: `data/scripts/projectiles/laser_emitter_start.lua` - The script responsible for initiating the laser emission.
*   **`execute_every_n_frame`**: `2` - The script runs every 2 frames.
*   **`remove_after_executed`**: `1` - The script is removed after its first execution.

## Variable Storage (`VariableStorageComponent`)

Stores custom variables within the entity.

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/deck/orb_laseremitter_weak.xml` - Stores the path to this entity's XML file, useful for referencing.