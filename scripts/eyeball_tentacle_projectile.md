---
title: Eyeball Tentacle Projectile
category: scripts
---

# Eyeball Tentacle Projectile

This script defines the behavior for the projectile fired by the Eyeball Tentacle enemy in Noita. It focuses on loading the projectile entity and setting its initial velocity.

## Key Components

### Projectile Loading

*   **`EntityLoad("data/entities/projectiles/tentacle.xml", pos_x, pos_y)`**: This is the core function that loads the `tentacle.xml` entity, which defines the visual and physical properties of the projectile. It's placed at the Eyeball Tentacle's current position.

### Velocity Configuration

*   **`vel_x = 200`**: Sets the initial horizontal velocity of the projectile.
*   **`vel_y = 200`**: Sets the initial vertical velocity of the projectile.
*   **`edit_component( entity_id, "VelocityComponent", ...)`**: This function modifies the `VelocityComponent` of the loaded projectile.
    *   **`ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y )`**: Directly sets the `mVelocity` property of the `VelocityComponent` to the defined `vel_x` and `vel_y` values, making the projectile move.

### Shooter Identification

*   **`get_herd_id( entity_id )`**: Retrieves the herd ID of the entity that fired this projectile. This is important for game mechanics like friendly fire and AI targeting.
*   **`edit_component( entity_id, "ProjectileComponent", ...)`**: Modifies the `ProjectileComponent` of the projectile.
    *   **`vars.mWhoShot = entity_id`**: Records the ID of the entity that fired this projectile.
    *   **`vars.mShooterHerdId = herd_id`**: Records the herd ID of the shooter.

## Summary

This script is a straightforward projectile spawner. It loads a pre-defined projectile entity and immediately gives it a consistent upward and rightward velocity. It also tags the projectile with information about its shooter, which is crucial for gameplay interactions.