---
title: Polyp Trajectory Velocity Adjustment
category: entities
---

---

# Polyp Trajectory Velocity Adjustment

This script modifies the velocity of an entity, specifically designed for the "polyp_trajectory" entity, likely a projectile or movement component of a boss ghost. It introduces a random adjustment to the existing velocity, making its trajectory slightly unpredictable.

## Key Functionality

### Velocity Modification

The core of the script lies in its ability to dynamically alter the `mVelocity` of a `VelocityComponent`.

*   **`edit_component( entity_id, "VelocityComponent", function(comp,vars) ... end)`**: This function targets and modifies the `VelocityComponent` associated with the entity.
*   **`local vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity")`**: Retrieves the current X and Y components of the entity's velocity.
*   **`local scale = math.max( math.abs( vel_x ), math.abs( vel_y ) ) * 0.4`**: Calculates a scaling factor for the random adjustment. This scale is proportional to the magnitude of the current velocity, ensuring that faster-moving entities receive a larger potential random deviation. The multiplier `0.4` controls the maximum possible deviation relative to the current speed.
*   **`local random_adjustment = Random( 0 - scale, scale )`**: Generates a random floating-point number between `-scale` and `scale`. This value will be added to both the X and Y velocity components.
*   **`vel_x = vel_x + random_adjustment`**: Adds the random adjustment to the X velocity.
*   **`vel_y = vel_y + random_adjustment`**: Adds the random adjustment to the Y velocity.
*   **`ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y)`**: Updates the entity's velocity with the newly calculated, slightly randomized values.

## Initialization

*   **`dofile_once( "data/scripts/lib/utilities.lua" )`**: Ensures that utility functions are loaded and available.
*   **`local entity_id = GetUpdatedEntityID()`**: Retrieves the unique identifier for the entity being processed.
*   **`local pos_x, pos_y = EntityGetTransform( entity_id )`**: Gets the current position of the entity.
*   **`SetRandomSeed( GameGetFrameNum(), pos_x + pos_y + entity_id )`**: Initializes the random number generator. Using the current frame number, entity position, and entity ID ensures a different sequence of random numbers for each entity and each frame, contributing to the unpredictable nature of the trajectory.