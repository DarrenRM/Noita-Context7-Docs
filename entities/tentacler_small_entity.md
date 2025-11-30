---
title: Tentacler Small Entity
category: entities
---

# Tentacler Small Entity

This document describes the `tentacler_small.xml` entity, a small tentacler creature in Noita.

## Key Attributes

### Base Entity
The `tentacler_small.xml` entity inherits its core properties from `data/entities/animals/tentacler_small.xml`.

### Damage Component
*   **hp**: 3 (Current health)
*   **max_hp**: 3 (Maximum health)
*   **minimum_knockback_force**: 100000 (A very high value, indicating significant resistance to being knocked back)

### Attached Tentacle
This entity includes a child entity representing a tentacle, defined by:
*   **Base file**: `data/entities/verlet_chains/smalltentacle/tentacler_tentacle_02.xml`
*   **Inherited Transform**: The tentacle is positioned relative to the main entity.
    *   **position.x**: 0
    *   **position.y**: -8