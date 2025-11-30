---
title: Ominous Orb - Black Hole Projectile Spawner
category: scripts
---

# Ominous Orb - Black Hole Projectile Spawner

This script defines the behavior of an "Ominous Orb" entity in Noita. When triggered by a collision, it spawns a large black hole projectile and then destroys itself.

## Key Functionality

### `collision_trigger()`

This function is the core logic of the Ominous Orb. It is called when the entity collides with something.

*   **Spawns Black Hole:** It loads the `data/entities/projectiles/deck/black_hole_big.xml` entity at the orb's current position. This effectively creates a large black hole projectile.
*   **Self-Destruction:** After spawning the projectile, the orb entity is destroyed using `EntityKill(entity_id)`.

## Attributes (Implicit)

While not explicitly defined in this snippet, the Ominous Orb entity would likely have the following attributes configured in its corresponding `.xml` file:

*   **Collision Component:** To enable the `collision_trigger` function to be called.
*   **Visuals/Sprite:** To represent the orb in the game world.
*   **Position/Transform:** To define its initial placement.

## Related Files

*   `data/entities/projectiles/deck/black_hole_big.xml`: The entity definition for the black hole projectile that is spawned.