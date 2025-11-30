---
title: Arrow Trap (Right) Entity
category: entities
---

---

# Arrow Trap (Right) Entity

This document describes the `arrowtrap_right.xml` entity, a building entity in Noita used for creating right-facing arrow traps. It inherits its base functionality from `arrowtrap_left.xml` and adds specific visual and functional components.

## Key Components

### Base Entity (`<Base file="data/entities/buildings/arrowtrap_left.xml">`)

This tag indicates that `arrowtrap_right.xml` inherits most of its properties from `arrowtrap_left.xml`.

### Sprite Component (`<SpriteComponent>`)

*   **`image_file`**: `data/buildings_gfx/arrowtrap_right.xml`
    *   Specifies the graphical asset used for the right-facing arrow trap.

### Hitbox Component (`<HitboxComponent>`)

*   **`_enabled`**: `1`
    *   Enables the hitbox for this entity.
*   **`aabb_min_x`**: `-5`
    *   Minimum X-coordinate of the Axis-Aligned Bounding Box.
*   **`aabb_max_x`**: `0`
    *   Maximum X-coordinate of the Axis-Aligned Bounding Box.
*   **`aabb_min_y`**: `-5`
    *   Minimum Y-coordinate of the Axis-Aligned Bounding Box.
*   **`aabb_max_y`**: `5`
    *   Maximum Y-coordinate of the Axis-Aligned Bounding Box.
    *   These values define the collision area for the trap.

### Pixel Scene Component (`<PixelSceneComponent>`)

*   **`pixel_scene`**: `data/biome_impl/crypt/trap_frame_right.png`
    *   References a pixel scene file, likely used for detailed visual representation or interaction within the trap's frame.
*   **`offset_x`**: `-15`
    *   Horizontal offset for the pixel scene.
*   **`offset_y`**: `-10`
    *   Vertical offset for the pixel scene.

### Additional Entities (Protections)

The entity contains two nested entities, each providing a specific protection effect to anything interacting with the trap.

#### Entity 1 (Freeze Protection)

*   **`GameEffectComponent`**:
    *   **`effect`**: `STUN_PROTECTION_FREEZE`
        *   Grants immunity to freeze effects.
    *   **`frames`**: `-1`
        *   Indicates the protection is permanent.

#### Entity 2 (Electricity Protection)

*   **`GameEffectComponent`**:
    *   **`effect`**: `STUN_PROTECTION_ELECTRICITY`
        *   Grants immunity to electricity effects.
    *   **`frames`**: `-1`
        *   Indicates the protection is permanent.