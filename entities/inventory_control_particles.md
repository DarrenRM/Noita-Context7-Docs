---
title: Inventory Control Particles
category: entities
---

# Inventory Control Particles

This entity defines particles used for inventory controls, specifically for visual feedback when interacting with inventory items.

## Entity Tags

*   `controls_inventory`: Identifies this entity as related to inventory controls.

## ParticleEmitterComponent

This component manages the emission of particles.

### Key Attributes:

*   `emitted_material_name`: Specifies the material of the emitted particles (e.g., "spark").
*   `lifetime_min`, `lifetime_max`: Duration of each emitted particle in seconds.
*   `count_min`, `count_max`: Number of particles emitted per emission event.
*   `render_on_grid`: Whether particles should be rendered on the game grid.
*   `fade_based_on_lifetime`: If true, particles fade out as their lifetime decreases.
*   `area_circle_radius.min`, `area_circle_radius.max`: Defines the radius of the emission area. Set to 0 for a single point emission.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the frame interval between particle emissions.
*   `emit_cosmetic_particles`: If true, emits particles that are purely cosmetic.
*   `image_animation_file`: Path to the sprite sheet used for animating particles.
*   `image_animation_speed`: Speed of the image animation.
*   `image_animation_loop`: Whether the image animation should loop.
*   `is_emitting`: If true, the emitter is active.

## LifetimeComponent

This component defines the overall lifetime of the entity.

### Key Attributes:

*   `lifetime`: The total duration the entity (and its particles) will exist in seconds.