---
title: Swarm Fly Projectile
category: scripts/
---

# Swarm Fly Projectile

This script defines the behavior for the "Swarm Fly" projectile in Noita. It primarily modifies the projectile's velocity to introduce a random, erratic movement pattern.

## Key Attributes and Behavior

### Velocity Modification

The core functionality of this script is to add a random offset to the projectile's existing velocity.

*   **`edit_component( entity_id, "VelocityComponent", function(comp,vars) ... end)`**: This targets the `VelocityComponent` of the entity (the projectile).
*   **`local vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity")`**: Retrieves the current velocity vector of the projectile.
*   **`local scale = 20`**: Defines the maximum magnitude of the random adjustment that can be applied to the velocity.
*   **`local random_adjustment_x = Random( 0 - scale, scale )`**: Generates a random float between `-scale` and `scale` for the X-axis.
*   **`local random_adjustment_y = Random( 0 - scale, scale )`**: Generates a random float between `-scale` and `scale` for the Y-axis.
*   **`vel_x = vel_x + random_adjustment_x`**: Adds the random X adjustment to the current X velocity.
*   **`vel_y = vel_y + random_adjustment_y`**: Adds the random Y adjustment to the current Y velocity.
*   **`ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y)`**: Updates the projectile's velocity with the newly adjusted values.

### Initialization

*   **`dofile_once( "data/scripts/lib/utilities.lua" )`**: Ensures utility functions are loaded.
*   **`local entity_id = GetUpdatedEntityID()`**: Gets the unique identifier for the projectile entity.
*   **`local pos_x, pos_y = EntityGetTransform( entity_id )`**: Retrieves the projectile's current position.
*   **`SetRandomSeed( GameGetFrameNum() * entity_id, (pos_x + pos_y) * entity_id )`**: Seeds the random number generator to ensure varied behavior across different projectiles and game states. This makes the random adjustments less predictable and more organic.

## Summary

This script is a simple but effective way to create a "swarm" effect for projectiles by making them move in a less predictable, more erratic manner. The `scale` variable is the primary parameter to adjust for controlling the intensity of this random movement.