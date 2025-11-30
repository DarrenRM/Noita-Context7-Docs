---
title: EyeA Boss Limb Sprite
category: entities
---

# EyeA Boss Limb Sprite

This document details the sprite information for the "EyeA" boss limb entity in Noita.

## Sprite Definition

The primary sprite for the EyeA boss limb is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_limbs/eyeA.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `24` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `24` - Vertical offset of the sprite's origin.

## Animations

The EyeA boss limb utilizes several distinct animations, each defined by a `<RectAnimation>` tag.

### Animations List:

| Name      | Description      | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Loop |
| :-------- | :--------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :--- |
| `stand`   | Standing animation | 1           | 48          | 48           | 0.09       | 6              | 1    |
| `invisible` | Invisibility animation | 1           | 48          | 48           | 0.09       | 6              | 1    |
| `animate` | Walking/general animation | 6           | 48          | 48           | 0.13       | 6              | 0    |

### Animation Details:

*   **`stand`**: This animation likely represents the idle state of the boss limb. It consists of a single frame.
*   **`invisible`**: This animation is associated with the boss limb becoming invisible. It also uses a single frame.
*   **`animate`**: This is the primary animation for movement or general action. It comprises 6 frames, suggesting a short looping sequence for walking or other actions. The `loop="0"` attribute indicates it will play once and then stop, likely transitioning to another animation.

**Note**: The `pos_x` and `pos_y` attributes within each `<RectAnimation>` tag define the starting position of the animation frames within the sprite sheet. For `stand` and `animate`, `pos_y` is `0`, indicating they are in the first row of the sprite sheet. For `invisible`, `pos_y` is `48`, indicating it's in the second row (assuming each row is 48 pixels high).