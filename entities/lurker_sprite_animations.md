---
title: Lurker Sprite Animations
category: entities
---

# Lurker Sprite Animations

This document details the sprite animations for the "Lurker" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base properties for the Lurker's visual representation.

```xml
<Sprite
 filename="data/enemies_gfx/lurker.png"
 offset_x="10"
 offset_y="10"
 default_animation="stand" >
</Sprite>
```

### Key Attributes:

*   **`filename`**: The path to the sprite sheet image file.
*   **`offset_x`**, **`offset_y`**: Adjustments to the sprite's position relative to its origin.
*   **`default_animation`**: The animation that plays when the entity is first spawned or in its default state.

## Animation Definitions

The `<RectAnimation>` tags define individual animations for the Lurker. Many of these animations are identical in this configuration, suggesting they might be placeholders or share the same visual frames.

### Common Animation Attributes:

*   **`name`**: The identifier for the animation (e.g., "stand", "walk", "burn").
*   **`pos_x`**, **`pos_y`**: The starting position of the animation frames within the sprite sheet.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: The dimensions of each individual frame.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`loop`**: Whether the animation should repeat (`1` for true, `0` for false).

### Defined Animations:

| Animation Name | `frame_count` | `frame_width` | `frame_height` | `frame_wait` | `frames_per_row` | `loop` | Notes                               |
| :------------- | :------------ | :------------ | :------------- | :----------- | :--------------- | :----- | :---------------------------------- |
| `stand`        | 20            | 20            | 20             | 0.09         | 20               | 1      | Default animation.                  |
| `walk`         | 20            | 20            | 20             | 0.09         | 20               | 1      |                                     |
| `run`          | 20            | 20            | 20             | 0.09         | 20               | 1      | Copied from `walk`.                 |
| `burn`         | 20            | 20            | 20             | 0.09         | 20               | 1      | Copied from `walk`.                 |
| `fly_idle`     | 20            | 20            | 20             | 0.09         | 20               | 1      |                                     |
| `fly_move`     | 20            | 20            | 20             | 0.09         | 20               | 1      |                                     |

**Note:** For modding purposes, if you intend to create distinct visual sequences for "walk", "run", "burn", "fly_idle", or "fly_move", you will need to adjust the `pos_x`, `pos_y`, `frame_count`, and potentially `frames_per_row` to match the new frame layout in your custom sprite sheet. The current configuration uses the same frame data for multiple animations.