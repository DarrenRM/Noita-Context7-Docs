---
title: Green Orb Projectile Spawning
category: scripts
---

# Green Orb Projectile Spawning

This script handles the spawning of multiple green orb projectiles when a specific entity is activated. It creates a ring of projectiles around the shooter.

## Key Functionality

*   **Spawns Multiple Projectiles:** Creates a specified number of new projectile entities.
*   **Circular Formation:** Distributes the spawned projectiles in a circular pattern around the origin.
*   **Inherits Shooter Information:** Passes the shooter's ID and herd ID to the spawned projectiles.
*   **Applies Velocity:** Assigns a velocity to each spawned projectile, directing it outwards from the center.

## Core Attributes & Logic

### Spawning Parameters

*   `how_many`: The number of projectiles to spawn. Defaults to `8`.
*   `length`: The magnitude of the velocity applied to each projectile. Defaults to `100`.

### Spawning Loop

The script iterates `how_many` times to spawn each projectile.

*   **Sound Effect:** Plays the "duplicate" sound effect for each spawned projectile.
*   **Entity Loading:** Loads a new projectile entity using `EntityLoad("data/entities/projectiles/orb_green.xml", pos_x, pos_y)`.
*   **Projectile Component Setup:**
    *   Retrieves the `ProjectileComponent` of the newly spawned entity.
    *   Sets `mWhoShot` to the ID of the newly spawned projectile itself.
    *   Sets `mShooterHerdId` to inherit the herd ID from the original shooter.
*   **Velocity Calculation:**
    *   Calculates the angle increment (`angle_inc`) for even distribution.
    *   Uses `math.cos(theta)` and `math.sin(theta)` to determine the `vel_x` and `vel_y` components of the velocity.
    *   Increments `theta` for the next projectile.
*   **Velocity Component Setup:**
    *   Retrieves the `VelocityComponent` of the newly spawned entity.
    *   Sets the `mVelocity` vector using `ComponentSetValueVector2`.

### Example Snippet (Velocity Calculation)

```lua
	local vel_x = math.cos( theta ) * length
	local vel_y = math.sin( theta ) * length
	theta = theta + angle_inc
```