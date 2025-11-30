---
title: Boss Limb Eye A Sprite
category: entities
---

# Boss Limb Eye A Sprite

This document details the sprite and animation data for the "Boss Limb Eye A" entity in Noita.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_limbs/eyeA.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `24` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `24` - Vertical offset of the sprite's origin.

## Animations

The entity utilizes several distinct animations, each defined by a `<RectAnimation>` tag.

### Animations List:

| Name      | Description     | Sprite Row | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Loop |
| :-------- | :-------------- | :--------- | :---------- | :---------- | :----------- | :--------- | :------------- | :--- |
| `stand`   | Standing pose   | 0          | 1           | 48          | 48           | 0.09       | 6              | 1    |
| `invisible` | Invisibility effect | 1          | 1           | 48          | 48           | 0.09       | 6              | 1    |
| `animate` | Walking/general animation | 0          | 6           | 48          | 48           | 0.13       | 6              | 0    |

### Animation Attributes:

*   **name**: The identifier for the animation (e.g., `stand`, `invisible`, `animate`).
*   **pos\_x**: The X-coordinate within the sprite sheet for the animation's starting frame.
*   **pos\_y**: The Y-coordinate within the sprite sheet for the animation's starting frame.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
*   **loop**: Determines if the animation should repeat (`1` for loop, `0` for no loop).