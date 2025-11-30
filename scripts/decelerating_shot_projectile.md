---
title: Decelerating Shot Projectile
category: scripts
---

---

# Decelerating Shot Projectile

This script modifies the `VelocityComponent` of a projectile, increasing its `air_friction` to cause it to decelerate over time.

## Key Attributes

*   **`air_friction`**: This is the primary attribute modified by the script. It's increased by a fixed value of `6`, causing the projectile to slow down more rapidly than it normally would.

## Script Logic

1.  **Get Entity ID**: Retrieves the unique identifier for the current entity.
2.  **Get Parent Entity**: Determines the entity that spawned this projectile. This is crucial for applying the effect to the projectile itself.
3.  **Target Entity Identification**:
    *   If the projectile has a parent (meaning it was fired by another entity), the `target_id` is set to the parent's ID.
    *   If the projectile has no parent (e.g., it's a standalone entity), the `target_id` is set to its own ID.
4.  **Projectile Component Check**: Verifies if the `target_id` entity possesses a `ProjectileComponent`. If not, the script exits.
5.  **Velocity Component Modification**:
    *   If a `ProjectileComponent` exists, the script targets the `VelocityComponent` of the `target_id`.
    *   It reads the current `air_friction` value.
    *   It adds `6` to the `air_friction`.
    *   The modified `air_friction` is then applied back to the `VelocityComponent`.

## Usage

This script is intended to be attached to a projectile entity. When the projectile is spawned, this script will run, directly impacting its movement by increasing its air friction and causing it to decelerate.