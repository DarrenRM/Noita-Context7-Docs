---
title: Mana Regeneration Effect Entity
category: entities
---

# Mana Regeneration Effect Entity

This entity defines the visual and functional components for a mana regeneration effect in Noita. It's primarily used to create a visual indicator and apply the mana regeneration buff to the player.

## Key Components

### ParticleEmitterComponent

This component handles the visual particles associated with the mana regeneration effect.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `emitted_material_name`   | The material used for the emitted particles (e.g., `magic_liquid_mana_regeneration`). |
| `lifetime_min`, `lifetime_max` | The minimum and maximum duration of each particle in seconds.            |
| `count_min`, `count_max`  | The minimum and maximum number of particles emitted per emission cycle.  |
| `area_circle_radius.max`  | The maximum radius of the circular area from which particles are emitted. |
| `x_vel_min`, `x_vel_max`  | The minimum and maximum horizontal velocity of emitted particles.        |
| `y_vel_min`, `y_vel_max`  | The minimum and maximum vertical velocity of emitted particles.          |
| `is_emitting`             | Controls whether the particle emitter is active (`1` for active).        |

### GameEffectComponent

This component applies the actual game effect to the entity.

| Attribute | Description                                                              |
| :-------- | :----------------------------------------------------------------------- |
| `effect`  | The type of game effect to apply. `MANA_REGENERATION` grants mana over time. |
| `frames`  | The duration of the effect in frames (e.g., `150` frames).               |

### InheritTransformComponent

This component ensures that the entity inherits the transform (position, rotation, scale) of its parent entity. This is crucial for effects that should follow the player or other objects.

```xml
<Entity>
	<ParticleEmitterComponent 
		emitted_material_name="magic_liquid_mana_regeneration"
		gravity.y="0.0"
		lifetime_min="1.2"
		lifetime_max="1.9"
		count_min="1"
		count_max="2"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.max="7"
		cosmetic_force_create="0"
		airflow_force="0.2"
		airflow_time="0.9"
		airflow_scale="0.15"
		emission_interval_min_frames="1"
		emission_interval_max_frames="2"
		emit_cosmetic_particles="1"
		x_vel_min="-10"
		x_vel_max="10"
		y_vel_min="-10"
		y_vel_max="10"
		is_emitting="1" >
	</ParticleEmitterComponent>
	
	<InheritTransformComponent 
		_enabled="1" >
    </InheritTransformComponent>	
    
    <GameEffectComponent 
        effect="MANA_REGENERATION"
        frames="150"
    >
	</GameEffectComponent >

</Entity>
```