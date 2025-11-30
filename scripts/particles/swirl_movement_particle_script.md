---
title: Swirl Movement Particle Script
category: scripts/particles
---

# Swirl Movement Particle Script

This script applies a swirling, wobbling movement to particles. It's designed to be attached to particle entities to give them dynamic, non-linear motion.

## Key Attributes and Behavior

The script modifies the `VelocityComponent` of an entity to achieve the swirling effect.

### Velocity Component Modification

The core logic resides within the `edit_component2` function, targeting the `VelocityComponent`.

*   **Steering:**
    *   `steer_limit`: Defines the maximum angle (in radians) the velocity can be rotated per frame.
    *   `steer_min`, `steer_max`: Sets a random range for the steering amount, ensuring variation in the swirl.
    *   `ProceduralRandomf(entity_id, 0, steer_min, steer_max)`: Generates a random steering value based on the entity's ID, providing consistent randomness for each particle.
    *   **Directional Bias:** `if entity_id%2 == 0 then steer = -steer end` applies an opposite steering direction for even-numbered entity IDs, creating a general outward or inward swirl pattern.

*   **Wobble Effect:**
    *   `wobble_size`: Controls the frequency of the sine wave used for the wobble.
    *   `wobble_amp`: Determines the amplitude (intensity) of the wobble.
    *   `wobble = math.sin((x + entity_id)*wobble_size) * wobble_amp + math.sin(y*wobble_size) * wobble_amp`: This line adds a sinusoidal wobble to the steering, making the particle's path undulate. It uses both X and Y coordinates, along with the entity ID, to create a complex, organic wobble.

*   **Velocity Update:**
    *   `vx, vy = vec_rotate(vx, vy, steer)`: Rotates the current velocity vector by the calculated `steer` value.
    *   `ComponentSetValue2( comp, "mVelocity", vx, vy)`: Updates the entity's velocity with the newly calculated swirling and wobbling vector.

### Camera Bounds Check

*   `if is_in_camera_bounds(x, y, 16) then ... end`: This conditional ensures that the script's logic is only applied when the particle is within the camera's view (with a buffer of 16 pixels). This is a performance optimization to avoid unnecessary calculations for off-screen particles.