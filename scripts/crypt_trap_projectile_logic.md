---
title: Crypt Trap Projectile Logic
category: scripts
---

# Crypt Trap Projectile Logic

This script defines the behavior for a "crypt trap" entity in Noita, specifically how it detects and attacks the player with projectiles. It determines the type of projectile to fire and its velocity based on the player's proximity and the trap's facing direction.

## Key Components and Logic

### Player Detection and Proximity Check

*   **`entity_id`**: The unique identifier for the crypt trap entity.
*   **`player_id`**: Retrieves the closest player entity to the trap.
*   **Proximity Check**: The trap attacks if the player is within a horizontal range of 170 units and a vertical range that varies based on the projectile type.

### Projectile Type Determination

The script inspects the `attack_ranged_entity_file` property of the `AnimalAIComponent` to identify the projectile.

*   **`projectile`**: Stores the filename of the projectile to be fired.
*   **Vertical Distance (`ydist`) Adjustment**:
    *   `40` units if projectile contains "fire" or "spit".
    *   `18` units if projectile contains "arrow".
    *   Default is `25` units.

### Directional Aiming

The trap aims at the player based on its sprite's facing direction.

*   **`SpriteComponent` Inspection**: The `image_file` property is checked to determine if the trap is facing right or left.
    *   `right.xml` implies facing right (`dir = 1`).
    *   `left.xml` implies facing left (`dir = -1`).
*   **Aiming Condition**: The trap will only fire if its facing direction aligns with the player's relative position (e.g., facing right and player is to the right).

### Projectile Velocity Calculation

The velocity of the projectile is adjusted based on its type.

*   **`velocity`**: The base speed of the projectile.
*   **Velocity Adjustments**:
    *   **Arrows**: Random velocity between 300 and 400.
    *   **Fire**: `320`.
    *   **Thunder**: `50`.
    *   **Spit**: `360`.
*   **Directional Vector**: Calculates the `vel_x` and `vel_y` components using `math.atan2` to aim directly at the player.
*   **Arrow Vertical Offset**: For arrows, `vel_y` is further reduced by `50` for a slight downward arc.

### Projectile Firing

*   **`shoot_projectile( entity_id, projectile, x, y + 2, vel_x, vel_y )`**: This function is called to instantiate and launch the projectile.
    *   `entity_id`: The trap entity firing the projectile.
    *   `projectile`: The projectile's entity file.
    *   `x, y + 2`: The spawn position of the projectile (slightly above the trap's center).
    *   `vel_x, vel_y`: The calculated velocity components.