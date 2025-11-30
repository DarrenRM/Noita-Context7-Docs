---
title: Workshop Guardian Spawn Position
category: entities
---

# Workshop Guardian Spawn Position

This entity defines a spawn position for the Workshop Guardian. It's primarily used for debugging and visual representation.

## Key Components

### SpriteComponent

This component is responsible for the visual representation of the spawn position.

*   **`_enabled`**: Set to `0`, meaning this sprite is not visible in-game. This is typical for debug entities.
*   **`alpha`**: `1` (fully opaque), though not visible due to `_enabled`.
*   **`offset_x`, `offset_y`**: `0`, indicating no positional offset for the sprite.
*   **`image_file`**: `data/debug/box_10x10.png`. This points to a simple 10x10 pixel box image, used for debugging visualization.

## Entity Tags

*   **`guardian_spawn_pos`**: This tag identifies the entity's purpose as a spawn point for the Workshop Guardian.

---