---
title: Workshop Allow Mods Entity
category: entities
---

# Workshop Allow Mods Entity

This document describes the `workshop_allow_mods.xml` entity, which represents a workshop object in Noita that is specifically designed to allow modding.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag.

```xml
<Entity tags="workshop">
  <!-- Components go here -->
</Entity>
```

### Key Attributes:

*   **`tags="workshop"`**: This tag is crucial as it identifies the entity as a workshop, likely enabling specific game mechanics or interactions related to modding and crafting.

## Components

This entity utilizes the following components:

### HitboxComponent

Defines the physical boundaries of the workshop entity.

```xml
<HitboxComponent
  aabb_min_x="-450"
  aabb_min_y="-124"
  aabb_max_x="64"
  aabb_max_y="32" >
</HitboxComponent>
```

#### Key Attributes:

*   **`aabb_min_x`, `aabb_min_y`**: The minimum X and Y coordinates of the bounding box.
*   **`aabb_max_x`, `aabb_max_y`**: The maximum X and Y coordinates of the bounding box.

This component defines the collision and interaction area for the workshop.