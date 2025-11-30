---
title: Debug Rain Particle Emitter
category: entities
---

# Debug Rain Particle Emitter

This entity defines a simple particle emitter designed to simulate rain. It's primarily for debugging purposes and can be used to test particle effects.

## Key Components

### ParticleEmitterComponent

This component is responsible for generating and managing the particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles to be emitted (e.g., "water").                |
| `x_pos_offset_min`        | Minimum horizontal offset for particle emission.                            |
| `x_pos_offset_max`        | Maximum horizontal offset for particle emission.                            |
| `y_pos_offset_min`        | Minimum vertical offset for particle emission.                              |
| `y_pos_offset_max`        | Maximum vertical offset for particle emission.                              |
| `count_min`               | Minimum number of particles emitted per emission interval.                  |
| `count_max`               | Maximum number of particles emitted per emission interval.                  |
| `lifetime_min`            | Minimum lifetime of emitted particles in seconds.                           |
| `lifetime_max`            | Maximum lifetime of emitted particles in seconds.                           |
| `airflow_force`           | The force applied to particles by airflow.                                  |
| `is_trail`                | If set to 1, particles will leave a trail.                                  |
| `emission_interval_min_frames` | Minimum frames between particle emissions.                                |
| `emission_interval_max_frames` | Maximum frames between particle emissions.                                |
| `create_real_particles`   | If set to 1, actual game particles are created.                             |
| `is_emitting`             | If set to 1, the emitter is active.                                         |

## Example Usage (Conceptual)

This entity would typically be placed in the game world to observe the rain effect. For modding, you could:

*   **Modify `emitted_material_name`**: Change the type of particle being emitted (e.g., to "blood" for a different visual effect).
*   **Adjust offsets**: Control the area where the rain appears.
*   **Tweak `count` and `lifetime`**: Alter the density and duration of the rain.
*   **Experiment with `airflow_force`**: Simulate wind affecting the rain.

```xml
<Entity>
  	<ParticleEmitterComponent 
		emitted_material_name="water"
		offset.x="0"
		offset.y="0"
		x_pos_offset_min="-256"
		x_pos_offset_max="0"
		y_pos_offset_min="0"
		y_pos_offset_max="0"
		x_vel_min="0"
		x_vel_max="0"
		y_vel_min="0"
		y_vel_max="0"
		count_min="1"
		count_max="10"
		lifetime_min="0.2"
		lifetime_max="0.5"
		airflow_force="10.0"
		is_trail="1"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		emit_cosmetic_particles="0"
		create_real_particles="1"
		is_emitting="1" >
	</ParticleEmitterComponent>
</Entity>
```