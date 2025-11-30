---
title: Black Hole Projectile Configuration
category: scripts
---

---

# Black Hole Projectile Configuration

This script defines the behavior and properties of a "big" black hole projectile in Noita, primarily focusing on its dynamic scaling and interaction with its environment.

## Key Components and Attributes

### BlackHoleComponent

This component governs the core black hole mechanics.

*   **`radius`**: Dynamically increases over time, capped at 64. This is the primary scaling factor for the black hole's influence.
*   **`particle_attractor_force`**: Directly proportional to the `radius` (`radius * 0.25`), determining how strongly it pulls in particles.

### LooseGroundComponent

This component controls how the black hole interacts with loose ground entities.

*   **`max_distance`**: Set to `radius + 20`. This defines the maximum range at which the black hole can affect and pull in loose ground.

### ParticleEmitterComponent

This component manages the particles emitted by the black hole.

*   **`x_pos_offset_min` / `x_pos_offset_max`**: These values are set to `-radius` and `radius` respectively, defining the horizontal spread of emitted particles relative to the black hole's center.
*   **`y_pos_offset_min` / `y_pos_offset_max`**: Similar to the x-offsets, these are set to `-radius` and `radius`, defining the vertical spread of emitted particles.

## Script Logic

The script dynamically modifies the `radius` of the black hole over time. This increasing radius then influences:

1.  The strength of its particle attraction.
2.  The range at which it affects loose ground.
3.  The spatial distribution of particles it emits.

This creates a projectile that grows in power and area of effect as it persists.