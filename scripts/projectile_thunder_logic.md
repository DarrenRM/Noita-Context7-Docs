---
title: Projectile Thunder Logic
category: scripts
---

---

# Projectile Thunder Logic

This script defines the behavior of the "Thunder" projectile in Noita. When a Thunder projectile is active, it scans for other nearby projectiles. If another projectile is within a certain range, the Thunder projectile will:

1.  **Disable explosions** on the target projectile.
2.  **Spawn a new "Thunder Lightning" projectile** aimed directly at the target projectile.
3.  **Destroy the target projectile**.

This creates a chain reaction effect where Thunder projectiles can trigger and redirect other projectiles.

## Key Functionality

### Projectile Interaction

The core logic involves finding and interacting with other projectiles in the vicinity.

*   **Proximity Check:** It iterates through all entities tagged as "projectile".
*   **Distance Calculation:** Calculates the Manhattan distance (`math.abs( x - px ) + math.abs( y - py )`) and then the Euclidean distance (`math.sqrt( ( x - px ) ^ 2 + ( y - py ) ^ 2 )`) to determine if another projectile is close enough.
*   **Targeting:** If a projectile is within a 48-unit radius, it becomes a target.

### Target Projectile Modification

When a target projectile is identified, its explosion behavior is altered.

*   **Disable `on_death_explode`:** Prevents the target projectile from exploding when it dies.
*   **Disable `on_lifetime_out_explode`:** Prevents the target projectile from exploding when its lifetime expires.

### Spawning and Destruction

The Thunder projectile then creates a new projectile and destroys the original.

*   **Direction Calculation:** Determines the angle towards the target projectile using `math.atan2`.
*   **Velocity Calculation:** Calculates the velocity components (`vel_x`, `vel_y`) for the new projectile based on a speed of 6000.
*   **`shoot_projectile`:** Spawns a new projectile of type `data/entities/projectiles/deck/projectile_thunder_lightning.xml` at the target projectile's location with the calculated velocity.
*   **`EntityKill`:** Destroys the original target projectile.

## Key Attributes/Elements

*   **`entity_id`**: The unique identifier for the current Thunder projectile.
*   **`x`, `y`**: The current position of the Thunder projectile.
*   **`projectiles`**: A table containing the IDs of all entities tagged as "projectile".
*   **`distance`**: The calculated distance between the Thunder projectile and another projectile.
*   **`projectilecomponents`**: A table of `ProjectileComponent` components for a target projectile.
*   **`direction`**: The angle in radians towards the target projectile.
*   **`speed`**: The velocity magnitude for the spawned projectile (6000).
*   **`vel_x`, `vel_y`**: The calculated X and Y velocity components for the spawned projectile.
*   **`on_death_explode`**: A component value set to "0" to disable death explosions.
*   **`on_lifetime_out_explode`**: A component value set to "0" to disable lifetime-out explosions.
*   **`projectile_thunder_lightning.xml`**: The entity XML file for the projectile that is spawned.