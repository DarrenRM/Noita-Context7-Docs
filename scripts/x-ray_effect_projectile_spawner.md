---
title: X-Ray Effect Projectile Spawner
category: scripts
---

---

# X-Ray Effect Projectile Spawner

This script is responsible for spawning multiple "xray_effect" projectiles in a circular pattern around the entity that executes it. It's designed to be attached to an entity that should trigger this projectile spread.

## Key Functionality

*   **Projectile Spawning:** Creates a specified number of projectiles.
*   **Circular Spread:** Distributes projectiles evenly in a 360-degree arc.
*   **Rate Limiting:** Prevents the script from executing too frequently, ensuring a controlled rate of projectile generation.

## Core Attributes

### `how_many`

*   **Type:** Number
*   **Description:** Determines the total number of "xray_effect" projectiles to spawn.
*   **Example:** `local how_many = 12` (spawns 12 projectiles)

### `angle_inc`

*   **Type:** Number
*   **Description:** Calculates the angular increment between each projectile to ensure an even distribution. This is derived from `2 * pi / how_many`.

### `length`

*   **Type:** Number
*   **Description:** Defines the magnitude of the velocity for each spawned projectile. This effectively controls how far the projectiles travel initially.
*   **Example:** `local length = 400`

### `script_wait_frames`

*   **Type:** Function (internal utility)
*   **Description:** A utility function that introduces a delay between script executions. This is crucial for performance and gameplay balance, preventing rapid-fire projectile generation.
*   **Example:** `if script_wait_frames( entity_id, 10 ) then return end` (waits for 10 frames before allowing execution)

### `shoot_projectile`

*   **Type:** Function (internal utility)
*   **Description:** The core function used to spawn a projectile. It takes the source entity ID, the projectile XML path, the spawn position (x, y), and the projectile velocity (x, y) as arguments.
*   **Example:** `shoot_projectile( entity_id, "data/entities/projectiles/deck/xray_effect.xml", pos_x, pos_y, vel_x, vel_y )`

## Execution Flow

1.  **Get Entity Information:** Retrieves the ID and position of the entity executing the script.
2.  **Rate Limit Check:** Checks if enough frames have passed since the last execution. If not, the script exits.
3.  **Calculate Projectile Parameters:** Determines the number of projectiles to spawn (`how_many`), the angular separation (`angle_inc`), and the projectile velocity magnitude (`length`).
4.  **Loop and Spawn:** Iterates `how_many` times:
    *   Calculates the velocity vector (x, y) for the current projectile based on its angle.
    *   Calls `shoot_projectile` to spawn an "xray_effect" projectile with the calculated velocity.
    *   Updates the angle for the next projectile.