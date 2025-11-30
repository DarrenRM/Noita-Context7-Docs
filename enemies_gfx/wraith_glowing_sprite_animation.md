---
title: Wraith Glowing Sprite Animation
category: data/enemies_gfx
---

---

# Wraith Glowing Sprite Animation

This document details the sprite animations for the "wraith_glowing" enemy in Noita, as defined in its XML configuration file.

## Sprite Definition

The primary sprite for the wraith_glowing is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/wraith_glowing.png` - Specifies the image file containing the sprite frames.
*   **offset\_x**: `12` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `12` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the enemy spawns.

## Animations

The wraith_glowing utilizes several `RectAnimation` tags to define its visual states. Each animation block specifies how to extract frames from the sprite sheet.

### Animation Details:

All listed animations share the following common frame extraction parameters:

*   **pos\_x**: `0` - Starting X coordinate on the sprite sheet for frame extraction.
*   **pos\_y**: `0` - Starting Y coordinate on the sprite sheet for frame extraction.
*   **frame\_width**: `24` - Width of each individual animation frame.
*   **frame\_height**: `24` - Height of each individual animation frame.
*   **frames\_per\_row**: `6` - Number of frames arranged horizontally on the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop indefinitely.

#### Individual Animations:

| Animation Name | Frame Count | Frame Wait | Notes                               |
| :------------- | :---------- | :--------- | :---------------------------------- |
| `stand`        | `1`         | `0.23`     | Default idle animation.             |
| `walk`         | `1`         | `0.23`     | Used for walking movement.          |
| `run`          | `1`         | `0.23`     | Copied from `walk`.                 |
| `burn`         | `1`         | `0.23`     | Copied from `walk`.                 |
| `fly_idle`     | `1`         | `0.23`     | Used for flying idle state.         |
| `fly_move`     | `1`         | `0.23`     | Used for flying movement.           |

**Note:** For all listed animations, `frame_count` is `1`. This suggests that each animation state currently uses a single static frame from the sprite sheet, or the sprite sheet is designed such that all frames for these animations are located at the same `pos_x`, `pos_y` and are simply intended to be cycled through if `frame_count` were higher. Given the `frames_per_row` of `6`, it's likely the sprite sheet contains more frames than currently utilized by these specific animation definitions.