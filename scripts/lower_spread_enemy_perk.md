---
title: Lower Spread Enemy Perk
category: scripts
---

---

# Lower Spread Enemy Perk

This script defines a perk that modifies enemy projectiles to have zero spread.

## Functionality

The `shot` function is the core of this perk. When an entity with this perk is activated (presumably when it fires a projectile), this function is called.

### `shot(entity_id)`

*   **Purpose:** Modifies the projectile component of an entity to eliminate directional randomness.
*   **Parameters:**
    *   `entity_id`: The unique identifier of the entity.

### Key Actions:

1.  **Get Projectile Components:** It retrieves all `ProjectileComponent` instances attached to the given `entity_id`.
2.  **Iterate and Modify:** If projectile components are found, it iterates through each one.
3.  **Set Direction Randomness:** For each `ProjectileComponent`, it sets the `direction_random_rad` value to `0`. This effectively removes any random deviation from the projectile's intended direction, making it fire in a perfectly straight line.

## Usage

This script is intended to be used as a perk that can be applied to enemies. When an enemy with this perk fires, its projectiles will no longer have any spread.

## Example (Conceptual)

```lua
-- This is a conceptual example of how this perk might be applied to an enemy
-- The actual implementation would be within Noita's entity definition files.

-- Assuming an enemy entity has a perk component that references this script
-- and triggers the 'shot' function when it fires.

-- Example of a projectile component that would be affected:
-- {
--     id = "ProjectileComponent",
--     direction_random_rad = 0.1, -- Original spread
--     speed = 50,
--     -- ... other projectile properties
-- }

-- After the 'shot' function is called on this entity:
-- {
--     id = "ProjectileComponent",
--     direction_random_rad = 0, -- Spread is now zero
--     speed = 50,
--     -- ... other projectile properties
-- }
```