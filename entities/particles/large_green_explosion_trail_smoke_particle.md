---
title: Large Green Explosion Trail Smoke Particle
category: entities/particles
---

# Large Green Explosion Trail Smoke Particle

This entity defines a large, green smoke particle used in explosions, specifically for creating a trail effect. It inherits its base functionality from `base_smoke_trail.xml` and modifies its velocity and sprite properties.

## Key Components and Attributes

### Base Entity

*   **`Base file="data/entities/particles/particle_explosion/base_smoke_trail.xml"`**: Inherits core particle explosion behavior.

### Velocity Component

*   **`air_friction="8.0"`**: Controls how quickly the particle loses velocity due to air resistance. A higher value means faster deceleration.

### Set Start Velocity Component

*   **`randomize_speed.min="300"`**: The minimum initial speed of the particle.
*   **`randomize_speed.max="1200"`**: The maximum initial speed of the particle. This range allows for varied trail lengths and dynamics.

### Die If Speed Below Component

*   **`min_speed="40"`**: The particle will be destroyed if its speed drops below this threshold, preventing it from lingering indefinitely.

### Sprite Particle Emitter Component (Velocity Randomization)

*   **`randomize_velocity.min_y="-20"`**: Minimum vertical velocity added to the particle.
*   **`randomize_velocity.max_y="10"`**: Maximum vertical velocity added to the particle.
*   **`randomize_velocity.min_x="-10"`**: Minimum horizontal velocity added to the particle.
*   **`randomize_velocity.max_x="10"`**: Maximum horizontal velocity added to the particle. These attributes introduce slight, random deviations in the particle's trajectory, contributing to a more natural smoke trail.

### Sprite Particle Emitter Component (Sprite Definition)

*   **`sprite_file="data/particles/smoke_cloud_green_$[1-4].xml"`**: Specifies the sprite files to be used for this particle. The `$[1-4]` indicates that one of four variations of `smoke_cloud_green` sprites will be randomly chosen, adding visual variety to the smoke.