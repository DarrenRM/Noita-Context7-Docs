---
title: Torch Vegetation
category: data/vegetation
---

---

# Torch Vegetation

This documentation describes the `torch.xml` file, which defines the visual representation and animation for the torch vegetation in Noita.

## Sprite

The `Sprite` element defines the visual asset for the torch.

### Key Attributes:

*   **filename**: Specifies the path to the sprite image file (`data/vegetation/torch.png`).
*   **offset\_x**: Horizontal offset for the sprite.
*   **offset\_y**: Vertical offset for the sprite.

## RectAnimation

The `RectAnimation` element defines the animation for the torch.

### Key Attributes:

*   **name**: The name of the animation state, in this case, "stand".
*   **pos\_x**: Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual animation frame.
*   **frame\_height**: The height of each individual animation frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
*   **loop**: Indicates if the animation should loop (1 for true, 0 for false).