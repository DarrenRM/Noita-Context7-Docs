---
title: Wand Ghost with Sampo
category: entities
---

# Wand Ghost with Sampo

This entity represents a "Wand Ghost" that is specifically equipped with a Sampo. It inherits its base behavior from `wand_ghost_charmed.xml`.

## Key Attributes

*   **`tags`**: `mortal`, `hittable`, `homing_target`, `wand_ghost`, `this_is_sampo`
    *   These tags define its fundamental properties: it can be killed, damaged, targeted by homing effects, and specifically identifies it as a wand ghost carrying a Sampo.
*   **`name`**: `$animal_wand_ghost`
    *   The internal name for this entity.
*   **`Base file="data/entities/animals/wand_ghost_charmed.xml"`**:
    *   Indicates that this entity inherits all properties and behaviors from the `wand_ghost_charmed` entity. This is the primary source of its functionality.

### Inherited Components (from `wand_ghost_charmed.xml`)

While the specific components are not listed here, the `wand_ghost_charmed.xml` file would define its movement, AI, projectile firing capabilities, and interaction with the game world.

#### `CameraBoundComponent`

*   **`_enabled="0"`**: This component is explicitly disabled for this entity.
*   **`max_count="1000"`**: (Irrelevant as `_enabled` is 0)
*   **`distance="160000"`**: (Irrelevant as `_enabled` is 0)

This indicates that the camera-bound behavior, which might normally limit the number of entities or their distance from the camera, is not active for this specific Wand Ghost.