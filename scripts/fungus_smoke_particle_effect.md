---
title: Fungus Smoke Particle Effect
category: scripts
---

# Fungus Smoke Particle Effect

This script defines a particle effect triggered by a collision event, likely for a "fungus smoke" entity in Noita.

## `collision_trigger()` Function

This function is called when the entity associated with this script collides with something.

### Key Actions:

1.  **Play Sound:** Triggers a sound effect named "death_buildup" for the entity.
2.  **Add Particle Emitter:** Attaches a `ParticleEmitterComponent` to the entity to generate visual particles.

### `ParticleEmitterComponent` Attributes:

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material used for the emitted particles ("plasma\_fading\_pink").       |
| `x_pos_offset_min`/`max`  | Minimum and maximum horizontal offset for particle emission.                |
| `y_pos_offset_min`/`max`  | Minimum and maximum vertical offset for particle emission.                  |
| `x_vel_min`/`max`         | Minimum and maximum horizontal velocity for emitted particles.              |
| `y_vel_min`/`max`         | Minimum and maximum vertical velocity for emitted particles.                |
| `count_min`/`max`         | The range for the number of particles to emit per emission burst.           |
| `lifetime_min`/`max`      | The minimum and maximum lifespan (in seconds) of each emitted particle.     |
| `create_real_particles`   | If `false`, these are cosmetic particles and don't interact physically.     |
| `emit_cosmetic_particles` | If `true`, particles are purely visual.                                     |
| `emission_interval_min`/`max_frames` | The frame delay between particle emission bursts.                       |
| `airflow_force`           | The force applied to particles by airflow.                                  |
| `airflow_scale`           | A scaling factor for the airflow force.                                     |

```lua
dofile_once("data/scripts/lib/utilities.lua")

function collision_trigger()
	local entity_id    = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( entity_id )
	
	GameEntityPlaySound(entity_id, "death_buildup" )

	EntityAddComponent2( entity_id, "ParticleEmitterComponent", 
	{ 
		emitted_material_name="plasma_fading_pink",
		x_pos_offset_min=-4,
		y_pos_offset_min=-4,
		x_pos_offset_max=4,
		y_pos_offset_max=4,
		x_vel_min=-60,
		x_vel_max=60,
		y_vel_min=-120,
		y_vel_max=-40,
		count_min=9,
		count_max=15,
		lifetime_min=0.6,
		lifetime_max=3.8,
		create_real_particles=false,
		emit_cosmetic_particles=true,
		emission_interval_min_frames=1,
		emission_interval_max_frames=2,
		airflow_force=6,
		airflow_scale=1.0,
	} )
end
```