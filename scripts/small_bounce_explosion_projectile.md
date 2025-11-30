---
title: Small Bounce Explosion Projectile
category: scripts
---

---

# Small Bounce Explosion Projectile

This script modifies a projectile to trigger a small explosion effect upon bouncing.

## Key Functionality

The primary purpose of this script is to attach a specific explosion effect (`bounce_small_explosion.xml`) to a projectile's `ProjectileComponent` when it bounces.

### Core Attributes Modified

*   **`bounce_fx_file`**: This attribute within the `ProjectileComponent` is set to `"data/entities/projectiles/deck/bounce_small_explosion.xml"`. This specifies the entity file to be spawned as a visual effect when the projectile bounces.

## Script Logic

1.  **Initialization**:
    *   Retrieves the current entity ID and its transform (position).
    *   Identifies the parent entity of the projectile.

2.  **Target Identification**:
    *   Determines the `target_id`. If the projectile has a parent, the parent's ID is used. Otherwise, the projectile's own ID is used. This ensures the modification is applied to the entity that initiated the projectile or the projectile itself if it's a standalone entity.

3.  **Projectile Component Modification**:
    *   Checks if the `target_id` is valid and has a `ProjectileComponent`.
    *   If a `ProjectileComponent` exists, it uses the `edit_component` function to modify it.
    *   The `bounce_fx_file` within the `ProjectileComponent` is updated to point to the desired explosion effect.

## Dependencies

*   `data/scripts/lib/utilities.lua`: Provides utility functions, likely including `edit_component`.

## Usage

This script is intended to be attached to a projectile entity that should have a small explosion visual effect upon bouncing.