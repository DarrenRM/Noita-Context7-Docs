---
title: Base Electricity Card Visuals
category: data/entities
---

# Base Electricity Card Visuals

This document details the visual components of the "Base Electricity" custom card entity in Noita, focusing on its particle effects when held.

## Entity Structure

The `Base Electricity` entity primarily defines visual effects using particle emitters.

```xml
<Entity>
	<InheritTransformComponent
		_tags="enabled_in_world,enabled_in_hand" >
	  <Transform
		position.x="8"
		position.y="0" >
	  </Transform>
	</InheritTransformComponent>

	<SpriteParticleEmitterComponent ... >
	</SpriteParticleEmitterComponent>

	<ParticleEmitterComponent ... >
	</ParticleEmitterComponent>
</Entity>
```

### Key Components

*   **`InheritTransformComponent`**: This component ensures the entity's visual effects are present when the item is in the world or held by the player. The `Transform` sub-element positions the effects relative to the item.

*   **`SpriteParticleEmitterComponent`**: Responsible for emitting visual "spark" particles.
    *   `sprite_file`: Specifies the particle sprite to use (`data/particles/spark_electric.xml`).
    *   `emission_interval_min_frames`/`emission_interval_max_frames`: Controls the timing of particle emissions.
    *   `count_min`/`count_max`: Determines the number of particles emitted per interval.
    *   `randomize_rotation`: Adds variation to the particle's initial rotation.
    *   `randomize_position`: Offsets the particle's spawn position within a defined area.

*   **`ParticleEmitterComponent`**: Generates another type of particle, likely for a different visual effect.
    *   `emitted_material_name`: Defines the material of the emitted particles (`spark_blue`).
    *   `x_pos_offset_min`/`max`, `y_pos_offset_min`/`max`: Defines the area where particles are spawned relative to the emitter.
    *   `x_vel_min`/`max`, `y_vel_min`/`max`: Sets the initial velocity of the particles.
    *   `lifetime_min`/`max`: Controls how long each particle exists.
    *   `emit_cosmetic_particles`: Indicates these are purely visual effects.
    *   `is_emitting`: Ensures the emitter is active.