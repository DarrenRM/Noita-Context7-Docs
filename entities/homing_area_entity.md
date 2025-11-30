---
title: Homing Area Entity
category: entities
---

---

# Homing Area Entity

This entity defines a visual indicator for a homing area, typically used in conjunction with projectile behavior. It primarily consists of a visual component and a Lua script to manage its behavior.

## Entity Components

### LuaComponent

This component attaches a Lua script to the entity, controlling its dynamic behavior.

*   **`script_source_file`**: `data/scripts/projectiles/homing_area.lua` - Specifies the path to the Lua script responsible for the entity's logic.
*   **`execute_every_n_frame`**: `1` - The script will execute every frame.

### SpriteComponent

This component defines the visual representation of the homing area.

*   **`image_file`**: `data/particles/area_indicator_064_blue.png` - The texture file used for the sprite.
*   **`offset_x`**: `32` - Horizontal offset for the sprite.
*   **`offset_y`**: `32` - Vertical offset for the sprite.
*   **`z_index`**: `1.1` - Determines the rendering order of the sprite.
*   **`never_ragdollify_on_death`**: `1` - Ensures the sprite does not ragdoll when the entity is destroyed.
*   **`rect_animation`**: `spawn` - Specifies the animation to play on spawn.
*   **`next_rect_animation`**: `""` - No subsequent animation is defined.