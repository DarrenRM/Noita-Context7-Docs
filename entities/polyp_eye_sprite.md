---
title: Polyp Eye Sprite
category: guides
---

<Entity name="Polyp Eye">
  <Sprite
    filename="data/entities/animals/boss_ghost/polyp_eye.png"
    offset_x="9"
    offset_y="9"
    default_animation="stand"
  >
    <RectAnimation
      name="stand"
      pos_x="0"
      pos_y="0"
      frame_count="1"
      frame_width="18"
      frame_height="18"
      frame_wait="0.12"
      frames_per_row="4"
      loop="1"
    />
  </Sprite>
</Entity>
```

---
title: Polyp Eye Sprite
category: entities
---

# Polyp Eye Sprite

This documentation describes the sprite and animation data for the "Polyp Eye" entity in Noita.

## Sprite

The `Sprite` element defines the visual appearance and animation of the entity.

### Key Attributes:

*   **`filename`**: `data/entities/animals/boss_ghost/polyp_eye.png` - Path to the sprite image file.
*   **`offset_x`**: `9` - Horizontal offset for the sprite.
*   **`offset_y`**: `9` - Vertical offset for the sprite.
*   **`default_animation`**: `"stand"` - The animation to play by default.

## Animations

### `stand` Animation

This defines the "stand" animation for the Polyp Eye.

#### Key Attributes:

*   **`name`**: `"stand"` - The name of this animation.
*   **`pos_x`**: `"0"` - Starting X position within the sprite sheet for this animation.
*   **`pos_y`**: `"0"` - Starting Y position within the sprite sheet for this animation.
*   **`frame_count`**: `"1"` - The total number of frames in this animation.
*   **`frame_width`**: `"18"` - The width of each individual frame.
*   **`frame_height`**: `"18"` - The height of each individual frame.
*   **`frame_wait`**: `"0.12"` - The duration (in seconds) each frame is displayed before advancing.
*   **`frames_per_row`**: `"4"` - The number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `"1"` - Indicates that the animation should loop (1 for true, 0 for false).