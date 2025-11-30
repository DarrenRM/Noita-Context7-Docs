---
title: Spittrap Right Building Entity
category: entities
---

# Spittrap Right Building Entity

This document describes the `spittrap_right.xml` entity, which defines a right-facing spittrap building in Noita. It inherits its base properties from `spittrap_left.xml` and adds specific visual and functional components.

## Key Components

### Base Entity (`<Base file="data/entities/buildings/spittrap_left.xml">`)

This tag indicates that `spittrap_right.xml` inherits most of its properties from `spittrap_left.xml`. This is a common practice for creating variations of existing entities.

### AnimalAIComponent

This component likely controls the AI behavior of the spittrap, such as its targeting or movement patterns.

*   **`eye_offset_x`**: `-8` - Adjusts the horizontal position of the entity's "eyes" or detection point.

### SpriteComponent

Defines the visual appearance of the spittrap.

*   **`image_file`**: `"data/buildings_gfx/spittrap_right.xml"` - Specifies the graphical asset used for the right-facing spittrap.

### HitboxComponent

Determines the collision area of the spittrap.

*   **`_enabled`**: `1` - Enables the hitbox.
*   **`aabb_min_x`**: `-5` - Minimum X-coordinate of the Axis-Aligned Bounding Box.
*   **`aabb_max_x`**: `0` - Maximum X-coordinate of the Axis-Aligned Bounding Box.
*   **`aabb_min_y`**: `-5` - Minimum Y-coordinate of the Axis-Aligned Bounding Box.
*   **`aabb_max_y`**: `5` - Maximum Y-coordinate of the Axis-Aligned Bounding Box.

### PixelSceneComponent

This component allows for the integration of a pixel-based scene or effect.

*   **`pixel_scene`**: `"data/biome_impl/crypt/trap_frame_right.png"` - The path to the pixel scene asset, likely defining the visual frame or structure of the trap.
*   **`offset_x`**: `-15` - Horizontal offset for the pixel scene.
*   **`offset_y`**: `-10` - Vertical offset for the pixel scene.

## Additional Entities

The spittrap also contains two nested entities, each with a `GameEffectComponent`. These likely provide passive protective effects to the spittrap itself.

### Entity 1: Freeze Protection

*   **`InheritTransformComponent`**: Ensures this entity inherits the transform (position, rotation, scale) of its parent.
*   **`GameEffectComponent`**:
    *   **`effect`**: `"STUN_PROTECTION_FREEZE"` - Applies a protection effect against freezing.
    *   **`frames`**: `-1` - Indicates the effect is permanent or lasts indefinitely.

### Entity 2: Electricity Protection

*   **`InheritTransformComponent`**: Ensures this entity inherits the transform of its parent.
*   **`GameEffectComponent`**:
    *   **`effect`**: `"STUN_PROTECTION_ELECTRICITY"` - Applies a protection effect against electricity.
    *   **`frames`**: `-1` - Indicates the effect is permanent or lasts indefinitely.