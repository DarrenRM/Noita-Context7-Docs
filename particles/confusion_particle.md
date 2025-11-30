---
title: Confusion Particle
category: particles
---

---

# Confusion Particle

This documentation describes the `confusion.xml` file, which defines the visual appearance and animation of the "confusion" particle effect in Noita.

## Sprite

The `Sprite` element defines the visual asset for the particle.

### Key Attributes:

*   **`filename`**: Specifies the image file used for the particle's sprite (`data/particles/confusion.png`).
*   **`offset_x`**: Horizontal offset for the sprite.
*   **`offset_y`**: Vertical offset for the sprite.

### Animations:

The `Sprite` contains one or more animation definitions.

#### `stand` Animation

This animation defines the default visual sequence for the confusion particle.

##### Key Attributes:

*   **`name`**: The name of the animation (`stand`).
*   **`frame_count`**: The total number of frames in the animation (4).
*   **`frame_width`**: The width of each individual frame (7 pixels).
*   **`frame_height`**: The height of each individual frame (7 pixels).
*   **`frame_wait`**: The duration each frame is displayed before transitioning to the next (0.12 seconds).
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet (6).
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet (0).
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet (1).
*   **`shrink_by_one_pixel`**: A flag indicating if frames should be shrunk by one pixel (1, meaning true).