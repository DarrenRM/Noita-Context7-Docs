---
title: White Hole Big Projectile
category: scripts
---

# White Hole Big Projectile

This script defines the behavior for the "White Hole Big" projectile in Noita, focusing on its dynamic size and gravitational effects.

## Key Components and Attributes

This projectile primarily modifies its own properties and those of nearby entities based on its current `radius`.

### BlackHoleComponent

This component governs the projectile's gravitational pull and its visual particle emission.

*   **`radius`**: Dynamically increases over time, capped at 64. This value directly influences other properties.
*   **`particle_attractor_force`**: Calculated as `0 - radius * 0.25`. As the radius grows, the force pulling particles towards the center increases.

### LooseGroundComponent

This component affects how the projectile interacts with the environment, specifically loose ground.

*   **`max_distance`**: Set to `radius + 20`. This determines the maximum range at which the projectile can affect loose ground. A larger radius means it can affect ground further away.

### ParticleEmitterComponent

This component controls the emission of particles around the projectile, creating its visual effect.

*   **`x_pos_offset_min` / `x_pos_offset_max`**: Set to `0 - radius` and `radius` respectively. This defines the horizontal spread of emitted particles.
*   **`y_pos_offset_min` / `y_pos_offset_max`**: Set to `0 - radius` and `radius` respectively. This defines the vertical spread of emitted particles.

As the `radius` increases, the area affected by the projectile's gravity and the area where particles are emitted both expand.