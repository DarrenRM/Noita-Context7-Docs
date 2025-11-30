---
title: Crumbling Earth Projectile
category: scripts/projectiles
---

# Crumbling Earth Projectile

This script defines the behavior for a projectile that creates "loose chunks" upon impact.

## Core Functionality

The primary purpose of this projectile is to spawn a separate entity, `loose_chunks_projectile.xml`, at its impact location. This suggests a visual or physical effect of the ground crumbling or breaking apart.

## Key Attributes/Elements

*   **Entity Loading:** The script uses `EntityLoad` to instantiate `data/entities/misc/loose_chunks_projectile.xml`. This is the central action of the projectile.
*   **Positioning:** The `x` and `y` coordinates are obtained from the projectile's current transform using `EntityGetTransform( GetUpdatedEntityID() )`, ensuring the spawned entity appears precisely where the projectile hit.

## Related Files

*   `data/entities/misc/loose_chunks_projectile.xml`: This file likely defines the visual and physical properties of the "loose chunks" that are spawned.

## Usage Example

When a projectile with this script attached hits a surface, it will trigger the loading of `loose_chunks_projectile.xml` at that exact point.