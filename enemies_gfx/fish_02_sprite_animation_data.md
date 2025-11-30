---
title: Fish 02 Sprite Animation Data
category: data/enemies_gfx
---

# Fish 02 Sprite Animation Data

This document details the sprite animation data for the "fish_02" enemy in Noita, focusing on its graphical representation and animation states.

## Sprite Definition

The primary sprite definition for `fish_02` is as follows:

```xml
<Sprite 
	filename="data/enemies_gfx/fish_02.png" 
	offset_x="7" 
	offset_y="5"
  default_animation="stand" >
  <!-- ... animations ... -->
</Sprite>
```

### Key Sprite Attributes:

*   **`filename`**: Specifies the texture file used for the sprite (`data/enemies_gfx/fish_02.png`).
*   **`offset_x`**, **`offset_y`**: Defines the sprite's pivot point relative to its origin.
*   **`default_animation`**: Sets the animation state that plays when the sprite is first loaded (`stand`).

## Animation States

The `fish_02` sprite utilizes several `RectAnimation` elements to define different visual states. Each animation is defined by a set of frames within the sprite sheet.

### Animation Details:

| Animation Name   | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Loop |
| :--------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :--- |
| `stand`          | 4           | 10          | 10           | 0.5        | 10             | 1    |
| `walk`           | 4           | 10          | 10           | 0.1        | 10             | 1    |
| `jump_up`        | 4           | 10          | 10           | 0.3        | 10             | 1    |
| `jump_falling`   | 4           | 10          | 10           | 0.4        | 10             | 1    |
| `death`          | 1           | 10          | 10           | 0.082      | 10             | 0    |

### Key Animation Attributes:

*   **`name`**: The identifier for the animation state (e.g., `stand`, `walk`).
*   **`frame_count`**: The total number of frames in this animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame in pixels.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`loop`**: Determines if the animation should repeat (`1` for true, `0` for false).

**Note:** All animations share the same `pos_x` and `pos_y` of `0`, indicating they all start from the top-left corner of the sprite sheet. The `frames_per_row` is consistently `10`, suggesting a grid layout for the frames. The `death` animation is non-looping, playing only once.