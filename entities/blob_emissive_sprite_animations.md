---
title: Blob Emissive Sprite Animations
category: entities
---

# Blob Emissive Sprite Animations

This document details the sprite animations for the "blob_emissive" enemy in Noita, focusing on key attributes for modding purposes.

## Sprite Definition

The main sprite definition for the blob emissive.

```xml
<Sprite
 filename="data/enemies_gfx/blob_emissive.png"
 offset_x="7"
 offset_y="13"
 default_animation="stand" >
```

### Key Attributes:

*   **filename**: The path to the sprite sheet image.
*   **offset\_x, offset\_y**: Adjustments to the sprite's position relative to its origin.
*   **default\_animation**: The animation to play when the entity is idle or no other animation is specified.

## Animation Definitions

The following table summarizes the defined animations for the blob emissive.

| Animation Name | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Loop | Notes                               |
| :------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :--- | :---------------------------------- |
| `stand`        | 6           | 14          | 16           | 0.16       | 8              | 1    | Idle animation.                     |
| `walk`         | 6           | 14          | 16           | 0.1        | 8              | 1    | Movement animation.                 |
| `run`          | 6           | 14          | 16           | 0.1        | 8              | 1    | Copied from `walk`.                 |
| `burn`         | 6           | 14          | 16           | 0.1        | 8              | 1    | Copied from `walk`.                 |
| `jump_up`      | 3           | 14          | 16           | 0.082      | 8              | 0    | Animation for jumping upwards.      |
| `jump_fall`    | 2           | 14          | 16           | 0.082      | 8              | 0    | Animation for falling after jump.   |
| `land`         | 4           | 14          | 16           | 0.074      | 8              | 0    | Animation for landing.              |
| `attack`       | 5           | 20          | 16           | 0.08       | 8              | 0    | Attack animation. Frame width differs. |

### Key Attributes for `RectAnimation`:

*   **name**: The identifier for the animation.
*   **pos\_x, pos\_y**: The starting coordinates of the animation frames within the sprite sheet. These values are relative to the top-left corner of the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width, frame\_height**: The dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: The number of frames that fit horizontally in a single row of the sprite sheet. This is used to calculate the position of subsequent frames.
*   **loop**: `1` for looping animations, `0` for non-looping animations.