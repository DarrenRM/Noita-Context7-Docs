---
title: Purple Explosion Field Projectile
category: entities
---

# Purple Explosion Field Projectile

This entity defines a projectile that creates a persistent purple explosion field. It primarily relies on a Lua script to manage its behavior and a particle emitter to generate visual effects.

## Key Components

### ProjectileComponent

This component defines the core projectile properties.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `_enabled`                | Enables or disables the component (1 for enabled).                          |
| `lob_min`, `lob_max`      | Controls the lobbing behavior of the projectile (0.8 to 1.0 suggests minimal lob). |
| `speed_min`, `speed_max`  | Sets the projectile's speed (0 to 0 indicates it doesn't move on its own). |
| `on_death_explode`        | Whether the projectile explodes upon death (0 for no).                      |
| `on_death_gfx_leave_sprite` | Whether to leave a sprite graphic upon death (0 for no).                    |
| `on_lifetime_out_explode` | Whether the projectile explodes when its lifetime ends (0 for no).          |
| `explosion_dont_damage_shooter` | Prevents the explosion from damaging the shooter (0 for no).                |
| `on_collision_die`        | Whether the projectile dies upon collision (0 for no).                      |
| `damage`                  | The damage dealt by the projectile (0 for no direct damage).                |
| `lifetime`                | The duration of the projectile in frames (600 frames ≈ 10 seconds).         |

### LuaComponent

This component links the projectile to a custom Lua script for advanced behavior.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `script_source_file`| Path to the Lua script responsible for the projectile's logic.           |
| `execute_every_n_frame` | How often the Lua script is executed (11 frames).                        |

### ParticleEmitterComponent

This component defines the visual particles emitted by the projectile, creating the "purple explosion field" effect.

| Attribute                   | Description                                                                                                |
| :-------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `emitted_material_name`     | The material of the particles to be emitted ("spark_purple").                                              |
| `x_pos_offset_min/max`      | Minimum and maximum horizontal offset for particle emission.                                               |
| `y_pos_offset_min/max`      | Minimum and maximum vertical offset for particle emission.                                                 |
| `x_vel_min/max`             | Minimum and maximum horizontal velocity of emitted particles.                                              |
| `y_vel_min/max`             | Minimum and maximum vertical velocity of emitted particles.                                                |
| `gravity.y`                 | Vertical gravity applied to particles (0.0 for no gravity).                                                |
| `lifetime_min/max`          | Minimum and maximum lifetime of individual particles in seconds.                                           |
| `count_min/max`             | Minimum and maximum number of particles emitted per emission cycle.                                        |
| `render_on_grid`            | Whether particles should render on the game grid (1 for yes).                                              |
| `fade_based_on_lifetime`    | Whether particles fade out as their lifetime decreases (1 for yes).                                        |
| `cosmetic_force_create`     | Whether to force the creation of cosmetic particles (0 for no).                                            |
| `airflow_force`, `airflow_time`, `airflow_scale` | Parameters controlling airflow effects on particles.                                       |
| `emission_interval_min_frames/max_frames` | The range of frames between particle emission cycles.                                      |
| `emit_cosmetic_particles`   | Whether to emit cosmetic particles (1 for yes).                                                            |
| `is_emitting`               | Whether the particle emitter is currently active (1 for yes).                                              |

---
```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
   >

	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
			gravity_y="0"
			>
    	</VelocityComponent> 
	</Base>

  <ProjectileComponent 
    _enabled="1" 
  	lob_min="0.8"
  	lob_max="1.0"
    speed_min="0"
    speed_max="0"
    on_death_explode="0"
    on_death_gfx_leave_sprite="0" 
    on_lifetime_out_explode="0"
	explosion_dont_damage_shooter="0"
    on_collision_die="0"
	damage="0"
    lifetime="600" >
  </ProjectileComponent>
  
  <LuaComponent
	script_source_file="data/scripts/projectiles/purple_explosion_field.lua"
	execute_every_n_frame="11"
	>
  </LuaComponent>
  
  <ParticleEmitterComponent 
		emitted_material_name="spark_purple"
		x_pos_offset_min="-60"
		x_pos_offset_max="60"
		y_pos_offset_min="-60"
		y_pos_offset_max="60"
		x_vel_min="-2"
		x_vel_max="2"
		y_vel_min="-2"
		y_vel_max="2"
		gravity.y="0.0"
		lifetime_min="0.5"
		lifetime_max="20.5"
		count_min="2"
		count_max="4"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		cosmetic_force_create="0"
		airflow_force="0.05"
		airflow_time="0.11"
		airflow_scale="0.05"
		emission_interval_min_frames="3"
		emission_interval_max_frames="6"
		emit_cosmetic_particles="1"
		is_emitting="1" >
	</ParticleEmitterComponent>

</Entity>
```