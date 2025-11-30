---
title: Vacuum Projectile Behavior
category: scripts
---

---

# Vacuum Projectile Behavior

This script defines the behavior of a "vacuum" projectile in Noita. When this projectile is spawned, it pulls in nearby entities tagged as "hittable" or "projectile" towards its own position.

## Key Attributes

*   **`radius`**: The distance (in pixels) within which the vacuum effect operates. In this script, it's set to `64`.

## Core Logic

The script performs the following actions:

1.  **Get Entity ID and Position**: It retrieves the unique ID of the vacuum projectile entity and its current world coordinates (`x`, `y`).
2.  **Identify Nearby Entities**: It searches for entities within the specified `radius` that have either the `"hittable"` or `"projectile"` tag.
3.  **Apply Transform**: For each identified entity, it:
    *   Retrieves the entity's current transform (position and rotation).
    *   If the transform is valid, it sets the entity's transform to the vacuum projectile's position (`x`, `y`).
    *   Applies the transform, effectively moving the entity towards the vacuum projectile.

## Example Usage (Conceptual)

This script would typically be attached to a projectile entity. When this projectile hits something or is spawned, its associated script would execute, causing nearby objects to be pulled in.

```lua
-- Example of how this script might be triggered (not part of the provided code)
-- This would likely be part of a spell or weapon definition
{
    -- ... other projectile properties
    script = "data/scripts/projectiles/vacuum_entities.lua",
    -- ...
}
```

## Summary of Actions

The primary function of this script is to create a localized gravitational pull, drawing in specific types of entities towards the vacuum projectile's origin. This can be used for effects like pulling enemies or other projectiles towards a central point.