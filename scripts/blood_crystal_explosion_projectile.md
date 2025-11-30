---
title: Blood Crystal Explosion Projectile
category: scripts
---

# Blood Crystal Explosion Projectile

This script defines the behavior for the projectile spawned when a "blood crystal" entity explodes. It creates a burst of smaller projectiles.

## Key Functions

### `explode()`
This function is the core logic for the explosion.

*   **Timing:** It ensures the explosion logic only runs every 10 frames using `script_wait_frames`.
*   **Projectile Count:** Spawns a fixed number of `how_many` projectiles (defaulting to 12).
*   **Projectile Type:** Shoots projectiles defined by `"data/entities/projectiles/orb_pink.xml"`.
*   **Spread Pattern:** Distributes projectiles in a circular pattern around the originating entity.
*   **Velocity:** Assigns a consistent `length` (speed) to each projectile, with its direction determined by the angle.
*   **Offset:** Applies a small `dist` offset to the spawn position of each projectile to prevent self-collision.

### `collision_trigger()`
This function is called when the entity collides with something. It simply calls the `explode()` function to initiate the projectile burst.

## Key Attributes

| Attribute     | Description                                                              |
| :------------ | :----------------------------------------------------------------------- |
| `how_many`    | The number of projectiles to spawn in the explosion.                     |
| `angle_inc`   | The angular increment between spawned projectiles.                       |
| `theta`       | The current angle used for calculating projectile direction and position. |
| `length`      | The magnitude (speed) of the velocity for each spawned projectile.       |
| `dist`        | The radial distance from the explosion center to spawn projectiles.      |
| `projectile`  | The XML path to the projectile entity to be spawned (e.g., `orb_pink.xml`). |

## Example Usage

This script is typically attached to an entity that is designed to explode, such as a specific type of enemy or a destructible environmental object. When that entity's collision is triggered, this script will execute `collision_trigger()`, leading to the `explode()` function being called and the projectile burst occurring.