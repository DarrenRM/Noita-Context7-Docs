---
title: Entity Hitbox and Character Data Configuration
category: entities
---

# Entity Hitbox and Character Data Configuration

This document outlines key components for configuring entity hitboxes and character data in Noita modding, focusing on essential attributes for AI-assisted mod development.

## HitboxComponent

The `HitboxComponent` defines the physical boundaries of an entity.

### Key Attributes:

*   `aabb_min_x`: Minimum X-coordinate of the Axis-Aligned Bounding Box (AABB).
*   `aabb_max_x`: Maximum X-coordinate of the AABB.
*   `aabb_min_y`: Minimum Y-coordinate of the AABB.
*   `aabb_max_y`: Maximum Y-coordinate of the AABB.

**Example:**

```xml
<HitboxComponent
    _enabled="1"
    aabb_min_x="-4.5"
    aabb_max_x="4.5"
    aabb_min_y="-5.5"
    aabb_max_y="3"
>
</HitboxComponent>
```

**Note:** Use the in-game debug tools (F5 + N) to visually verify hitbox accuracy.

## CharacterDataComponent

The `CharacterDataComponent` stores various properties related to an entity's character-like behavior, including collision and buoyancy.

### Key Attributes:

*   `climb_over_y`: The vertical distance an entity can climb over obstacles.
*   `collision_aabb_min_x`: Minimum X-coordinate for collision detection.
*   `collision_aabb_max_x`: Maximum X-coordinate for collision detection.
*   `collision_aabb_min_y`: Minimum Y-coordinate for collision detection.
*   `collision_aabb_max_y`: Maximum Y-coordinate for collision detection.
*   `buoyancy_check_offset_y`: An offset applied to the entity's center for buoyancy checks, determining its floating height in liquids. A value of -6 means the check point is 6 pixels below the entity's center.

**Example:**

```xml
<CharacterDataComponent
    _enabled="1"
    climb_over_y="4"
    collision_aabb_min_x="-2.0"
    collision_aabb_max_x="2.0"
    collision_aabb_min_y="-3"
    collision_aabb_max_y="3"
    buoyancy_check_offset_y="-3">
</CharacterDataComponent>
```