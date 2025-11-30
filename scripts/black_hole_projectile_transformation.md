---
title: Black Hole Projectile Transformation
category: scripts
---

---

# Black Hole Projectile Transformation

This script modifies existing projectiles in Noita, transforming them into black holes under specific conditions. It iterates through all entities tagged as "projectile" and, if a projectile does not already possess the "black_hole" tag, it is converted.

## Key Functionality

The primary goal of this script is to:

1.  **Identify Projectiles:** Scan the game world for any entity tagged as "projectile".
2.  **Filter for Non-Black Holes:** Exclude projectiles that are already designated as black holes.
3.  **Transform Projectiles:** For eligible projectiles, it performs the following actions:
    *   Disables explosion effects upon death or lifetime expiration.
    *   Shoots a new "black_hole.xml" projectile from the original projectile's position and velocity.
    *   Destroys the original projectile.

## Core Components and Attributes

This script primarily interacts with and modifies components of projectile entities.

### Projectile Component Modifications

The script targets the `ProjectileComponent` to disable certain behaviors:

*   `on_death_explode`: Set to `"0"` to prevent explosions when the projectile is destroyed.
*   `on_lifetime_out_explode`: Set to `"0"` to prevent explosions when the projectile's lifespan ends.

### Velocity Component Handling

The script retrieves the velocity of the projectile using the `VelocityComponent`:

*   `mVelocity`: This attribute stores the projectile's current velocity vector (x, y). The script reads this value to apply it to the newly created black hole projectile.

### Projectile Creation and Destruction

*   `shoot_projectile_from_projectile`: This utility function is used to spawn a new projectile.
    *   **Source Entity:** `projectile_id` (the projectile being transformed).
    *   **Projectile XML:** `"data/entities/projectiles/deck/black_hole.xml"` (the template for the new black hole projectile).
    *   **Position:** `px`, `py` (the position of the original projectile).
    *   **Velocity:** `vel_x`, `vel_y` (the velocity of the original projectile).
*   `EntityKill( projectile_id )`: This function is called to destroy the original projectile after it has been transformed.

## Usage Context

This script is likely intended to be run periodically or upon specific game events to dynamically introduce black hole projectiles into the game world, potentially as a spell effect or environmental hazard.