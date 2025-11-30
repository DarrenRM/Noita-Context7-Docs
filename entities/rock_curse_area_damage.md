---
title: Rock Curse Area Damage
category: entities
---

# Rock Curse Area Damage

This entity defines an area that inflicts curse damage to entities within its bounds. It's primarily used for the "Rock Curse" effect.

## Key Components

### AreaDamageComponent

This component is responsible for applying damage to entities within a specified area.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `aabb_min.x`        | Minimum X-coordinate of the bounding box.                                   |
| `aabb_min.y`        | Minimum Y-coordinate of the bounding box.                                   |
| `aabb_max.x`        | Maximum X-coordinate of the bounding box.                                   |
| `aabb_max.y`        | Maximum Y-coordinate of the bounding box.                                   |
| `damage_per_frame`  | The amount of damage dealt per frame to entities within the area.           |
| `update_every_n_frame` | How often the damage check is performed (in frames).                        |
| `death_cause`       | The string ID for the cause of death when an entity is killed by this damage. |
| `damage_type`       | The type of damage being applied (e.g., `DAMAGE_CURSE`).                    |

### ParticleEmitterComponent

This component generates visual particles around the cursed area, enhancing the visual feedback of the effect.

| Attribute                 | Description                                                                                             |
| :------------------------ | :------------------------------------------------------------------------------------------------------ |
| `emitted_material_name`   | The material name of the particles to be emitted (e.g., `spark_red`).                                   |
| `x_pos_offset_min`        | Minimum X-offset for particle emission relative to the entity's position.                               |
| `x_pos_offset_max`        | Maximum X-offset for particle emission relative to the entity's position.                               |
| `y_pos_offset_min`        | Minimum Y-offset for particle emission relative to the entity's position.                               |
| `y_pos_offset_max`        | Maximum Y-offset for particle emission relative to the entity's position.                               |
| `x_vel_min`               | Minimum X-velocity of emitted particles.                                                                |
| `x_vel_max`               | Maximum X-velocity of emitted particles.                                                                |
| `y_vel_min`               | Minimum Y-velocity of emitted particles.                                                                |
| `y_vel_max`               | Maximum Y-velocity of emitted particles.                                                                |
| `gravity.y`               | The Y-component of gravity affecting the particles.                                                     |
| `lifetime_min`            | Minimum lifetime of emitted particles in seconds.                                                       |
| `lifetime_max`            | Maximum lifetime of emitted particles in seconds.                                                       |
| `count_min`               | Minimum number of particles emitted per emission burst.                                                 |
| `count_max`               | Maximum number of particles emitted per emission burst.                                                 |
| `emission_interval_min_frames` | Minimum frames between particle emission bursts.                                                        |
| `emission_interval_max_frames` | Maximum frames between particle emission bursts.                                                        |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles (particles that don't affect gameplay).                              |
| `is_emitting`             | Whether the particle emitter is currently active.                                                       |

### CameraBoundComponent

This component ensures the entity is only active when it's within a certain distance of the camera, optimizing performance.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `max_count` | Maximum number of this entity type that can be active simultaneously.    |
| `distance`  | The maximum distance from the camera for the entity to remain active.    |

```xml
<Entity name="rock_curse" tags="no_swap" >

	<AreaDamageComponent
		aabb_min.x="-250" 
		aabb_min.y="-250" 
		aabb_max.x="250" 
		aabb_max.y="250" 
		damage_per_frame="0.1"
		update_every_n_frame="6"
		death_cause="$damage_rock_curse"
		damage_type="DAMAGE_CURSE"
		>
	</AreaDamageComponent>
	
	<ParticleEmitterComponent 
		emitted_material_name="spark_red"
		x_pos_offset_min="-250"
		x_pos_offset_max="250"
		y_pos_offset_min="-250"
		y_pos_offset_max="250"
		x_vel_min="-2"
		x_vel_max="2"
		y_vel_min="-2"
		y_vel_max="2"
		gravity.y="0.0"
		lifetime_min="0.5"
		lifetime_max="20.5"
		count_min="3"
		count_max="11"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		cosmetic_force_create="0"
		airflow_force="0.05"
		airflow_time="0.11"
		airflow_scale="0.05"
		emission_interval_min_frames="1"
		emission_interval_max_frames="4"
		emit_cosmetic_particles="1"
		is_emitting="1" >
	</ParticleEmitterComponent>
	
	<CameraBoundComponent
	  max_count="10"
	  distance="2000">
	</CameraBoundComponent>

</Entity>
```