---
title: Physics Glass Shard 04
category: entities
---

---

# Physics Glass Shard 04

This document describes the `physics_glass_shard_04.xml` entity, a physics-enabled prop representing a shard of glass.

## Key Attributes

### Base Entity

The entity inherits its core functionality from `data/entities/base_item_physics.xml`.

### Physics Components

*   **`PhysicsBodyComponent`**:
    *   `on_death_really_leave_body`: Set to `1`, indicating that the physics body should persist even after the entity is considered "dead" or removed.

*   **`PhysicsImageShapeComponent`**:
    *   `centered`: Set to `1`, meaning the image is centered within its physics shape.
    *   `image_file`: Specifies the graphical asset for the shard: `"data/props_gfx/glass_shard_04.png"`.
    *   `material`: Defines the physics material as `"glass_box2d"`.

### Lifetime Component

*   **`LifetimeComponent`**:
    *   `lifetime`: The shard will exist for `360` game frames before disappearing.