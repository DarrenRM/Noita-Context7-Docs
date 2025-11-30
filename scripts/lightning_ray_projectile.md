---
title: Lightning Ray Projectile
category: scripts
---

---

# Lightning Ray Projectile

This script defines the behavior for a lightning ray projectile in Noita. It's designed to be a component of a spell that can generate additional lightning arcs.

## Key Attributes

*   **`entity_id`**: The unique identifier for the lightning ray entity.
*   **`pos_x`, `pos_y`**: The initial position of the lightning ray.
*   **`angle`**: A randomly generated angle (0-359 degrees) to determine the direction of the lightning.
*   **`length`**: The base length of the lightning ray, set to 3000 units.
*   **`vel_x`, `vel_y`**: Calculated velocity components based on the `angle` and `length`.

## Core Functionality

The primary function of this script is to:

1.  Obtain the current entity's ID and transform.
2.  Generate a random angle for the lightning's trajectory.
3.  Calculate the velocity vector for the lightning based on the random angle and a fixed length.
4.  **Crucially**, it uses `shoot_projectile_from_projectile` to spawn a secondary projectile (`lightning_extra_arcs.xml`) originating from the current lightning ray's position and traveling in the calculated direction. This implies the `lightning_ray.lua` script is likely a precursor or a component that triggers the actual visual and damaging lightning effect.