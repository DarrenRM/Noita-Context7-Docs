---
title: Mouse Controls Particle Emitter
category: entities
---

# Mouse Controls Particle Emitter

This entity defines a particle emitter that is triggered by mouse controls. It's designed to emit visual effects, likely for UI feedback or interactive elements.

## Key Components

### ParticleEmitterComponent

This is the core component responsible for generating particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `_enabled`                | Controls whether the emitter is active. Set to `0` (disabled) in this example. |
| `emitted_material_name`   | The material of the particles to be emitted (e.g., "spark").                |
| `gravity.y`               | The gravitational pull on the particles along the Y-axis.                   |
| `lifetime_min`, `lifetime_max` | The minimum and maximum lifespan of individual particles in seconds.        |
| `count_min`, `count_max`  | The minimum and maximum number of particles emitted per emission.           |
| `render_on_grid`          | Whether particles should be rendered on the game grid.                      |
| `fade_based_on_lifetime`  | If `1`, particles will fade out as their lifetime decreases.                |
| `area_circle_radius.min`, `area_circle_radius.max` | Defines the radius of the circular area from which particles are emitted. Set to `0` for a single point emission. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | The frame interval between particle emissions. Set to `1` for continuous emission. |
| `emit_cosmetic_particles` | If `1`, emits particles that are purely cosmetic and don't interact with gameplay. |
| `image_animation_file`    | The path to the image file used for animating the particles.                |
| `image_animation_speed`   | The speed at which the particle image animation plays.                      |
| `image_animation_loop`    | If `1`, the particle image animation will loop.                             |
| `is_emitting`             | Controls whether the emitter is actively emitting particles.                |
| `render_back`             | If `1`, particles will be rendered behind other game elements.              |

### LifetimeComponent

This component defines the overall lifespan of the entity itself.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `_enabled`| Controls whether the component is active. |
| `lifetime`| The lifespan of the entity in frames.     |

---
```xml
<Entity tags="controls_mouse">
	
  	<ParticleEmitterComponent 
		_enabled="0"
		emitted_material_name="spark"
		gravity.y="0.0"
		lifetime_min="0.5"
		lifetime_max="1"
		count_min="1"
		count_max="1"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.min="0"
		area_circle_radius.max="0"
		cosmetic_force_create="0"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		emit_cosmetic_particles="1"
		image_animation_file="data/particles/image_emitters/controls_mouse.png"
		image_animation_speed="5"
		image_animation_loop="1"
		is_emitting="1"
		render_back="1"
		>
	</ParticleEmitterComponent>

	<LifetimeComponent
		_enabled="0"
		lifetime="350"
		>
	</LifetimeComponent>

</Entity>
```