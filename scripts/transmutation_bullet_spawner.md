---
title: Transmutation Bullet Spawner
category: scripts
---

---

# Transmutation Bullet Spawner

This script is responsible for spawning a "transmutation bullet" projectile when attached to a parent entity. It calculates a random direction and velocity for the projectile.

## Key Functionality

*   **Spawns Projectile:** Creates an instance of `data/scripts/streaming_integration/entities/transmutation_bullet.xml`.
*   **Random Direction:** Determines a random angle (`theta`) between 1 and 360 degrees.
*   **Fixed Velocity Magnitude:** Uses a `length` of 300 for the projectile's velocity.
*   **Parent Entity Dependency:** Only spawns a projectile if it has a valid parent entity.

## Attributes

| Attribute      | Description                                                                 |
| :------------- | :-------------------------------------------------------------------------- |
| `entity_id`    | The unique identifier of the entity running this script.                    |
| `pos_x`, `pos_y` | The X and Y coordinates of the entity.                                      |
| `theta`        | The random angle in radians, determining the projectile's direction.        |
| `length`       | The magnitude of the projectile's velocity.                                 |
| `parent_id`    | The identifier of the entity that spawned this projectile spawner.          |
| `vel_x`, `vel_y` | The calculated X and Y components of the projectile's velocity.             |

## Usage

This script is typically attached to an entity that should periodically fire a transmutation bullet. The `shoot_projectile` function handles the actual creation and launching of the projectile.