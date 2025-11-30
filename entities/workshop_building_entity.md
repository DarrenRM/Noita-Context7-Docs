---
title: Workshop Building Entity
category: entities
---

# Workshop Building Entity

This document describes the `workshop.xml` entity, which represents a workshop building in Noita.

## Key Attributes

The `workshop.xml` entity primarily defines the physical presence and behavior of a workshop.

### `Entity`

The root element for the workshop entity.

*   **`tags`**: `workshop`, `workshop_untouched` - These tags likely categorize the entity for game logic and potentially for modding purposes.

### `HitboxComponent`

Defines the collision area of the workshop.

*   **`aabb_min_x`**: `-64` - The minimum X-coordinate of the bounding box.
*   **`aabb_min_y`**: `-64` - The minimum Y-coordinate of the bounding box.
*   **`aabb_max_x`**: `64` - The maximum X-coordinate of the bounding box.
*   **`aabb_max_y`**: `32` - The maximum Y-coordinate of the bounding box.

### `LoadEntitiesComponent`

This component is crucial as it dictates what other entities are loaded when this workshop is present.

*   **`entity_file`**: `data/entities/buildings/workshop_allow_mods.xml` - Specifies the XML file of another entity to load. In this case, it loads `workshop_allow_mods.xml`, which likely contains the actual functionality and visual representation of the mod-allowing workshop.
*   **`kill_entity`**: `0` - Indicates that the workshop entity itself should not be killed when the loaded entity is processed.
*   **`count.min`**: `1` - The minimum number of `workshop_allow_mods.xml` entities to load.
*   **`count.max`**: `1` - The maximum number of `workshop_allow_mods.xml` entities to load.

---