---
title: Fizzle Particle Effect
category: entities
---

# Fizzle Particle Effect

This document describes the configuration for a "Fizzle" particle effect in Noita, commonly used for small, dissipating visual effects.

## Entity Configuration

The core of the effect is defined within an `<Entity>` tag.

### Key Components

*   **`LifetimeComponent`**:
    *   `lifetime`: The total duration this entity (and its associated particles) will exist.
        *   **`3`**: The effect lasts for 3 seconds.

*   **`ParticleEmitterComponent`**: This component governs the creation and behavior of the particles that make up the effect.
    *   `emitted_material_name`: The material used for the particles.
        *   **`spark_white`**: Particles will be white sparks.
    *   `lifetime_min`, `lifetime_max`: The minimum and maximum lifespan of individual particles.
        *   **`0.05` to `0.2`**: Each spark lasts between 0.05 and 0.2 seconds.
    *   `x_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_min`, `y_pos_offset_max`: Defines the area around the emitter where particles can spawn.
        *   **`-2` to `2`**: Particles spawn within a small square area.
    *   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: The initial velocity range for spawned particles.
        *   **`x_vel_min="-100"`, `x_vel_max="0"`**: Particles move leftwards, with varying speed.
        *   **`y_vel_min="-100"`, `y_vel_max="100"`**: Particles have vertical velocity, moving both up and down.
    *   `gravity.y`: The gravitational pull on the particles.
        *   **`0.0`**: Particles are not affected by gravity.
    *   `count_min`, `count_max`: The number of particles emitted per emission cycle.
        *   **`14` to `25`**: Between 14 and 25 sparks are emitted at once.
    *   `render_on_grid`: Whether particles should be rendered on the game grid.
        *   **`1`**: Particles are rendered.
    *   `fade_based_on_lifetime`: If particles should fade out as their lifetime ends.
        *   **`1`**: Particles will fade.
    *   `cosmetic_force_create`: Forces the creation of cosmetic particles, even if other conditions aren't met.
        *   **`0`**: Not forced.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: The frame delay between particle emissions.
        *   **`1`**: Particles are emitted continuously with no delay between frames.
    *   `emit_cosmetic_particles`: Whether to emit cosmetic particles.
        *   **`1`**: Cosmetic particles are emitted.
    *   `is_emitting`: Whether the emitter is currently active.
        *   **`1`**: The emitter is active.

```xml
<Entity>
    <LifetimeComponent
		lifetime="3"
		>
	</LifetimeComponent>

    <ParticleEmitterComponent 
		emitted_material_name="spark_white"
		gravity.y="0.0"
		lifetime_min="0.05"
		lifetime_max="0.2"
		x_pos_offset_min="-2"
		x_pos_offset_max="2"
		y_pos_offset_min="-2"
		y_pos_offset_max="2"
		x_vel_min="-100"
		x_vel_max="0"
		y_vel_min="-100"
		y_vel_max="100"
		gravity.y="0.0"
		count_min="14"
		count_max="25"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		cosmetic_force_create="0"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		emit_cosmetic_particles="1"
		is_emitting="1" >
	</ParticleEmitterComponent>
</Entity>
```