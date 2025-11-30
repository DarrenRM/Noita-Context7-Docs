---
title: Necromancer Shop Emissive Sprite Animations
category: entities
---

# Necromancer Shop Emissive Sprite Animations

This document details the sprite animations for the Necromancer Shopkeeper's emissive sprite in Noita, intended for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base properties of the sprite and its associated animations.

### Key Attributes:

*   **filename**: `data/enemies_gfx/necromancer_shop_emissive.png` - The texture file used for this sprite.
*   **offset_x**: `13` - Horizontal offset for the sprite's origin.
*   **offset_y**: `24` - Vertical offset for the sprite's origin.
*   **default_animation**: `"stand"` - The animation that plays by default.

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation sequence.

### Common Attributes for `RectAnimation`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack_ranged").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **pos\_x**: The X-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **loop**: `0` indicates the animation does not loop (plays once), while omitting it or setting to `1` implies looping.
*   **shrink\_by\_one\_pixel**: `1` indicates that each frame is shrunk by one pixel from its original dimensions.

### Defined Animations:

| Animation Name       | Frame Count | Frame Size (WxH) | Frames Per Row | Frame Wait (s) | Loop | Pos (X,Y) | Notes                     |
| :------------------- | :---------- | :--------------- | :------------- | :------------- | :--- | :-------- | :------------------------ |
| `stand`              | 6           | 32x32            | 6              | 0.1            | Yes  | (0,1)     | Default idle animation.   |
| `walk`               | 6           | 32x32            | 6              | 0.085          | Yes  | (0,1)     | Walking animation.        |
| `run`                | 6           | 32x32            | 6              | 0.085          | Yes  | (0,1)     | Running animation.        |
| `burn`               | 6           | 32x32            | 6              | 0.085          | Yes  | (0,1)     | Burning animation.        |
| `fly_idle`           | 6           | 32x32            | 15             | 0.12           | Yes  | (0,1)     | Flying idle animation.    |
| `fly_move`           | 6           | 32x32            | 15             | 0.12           | Yes  | (0,1)     | Flying movement animation.|
| `attack_ranged`      | 8           | 33x33            | 8              | 0.04           | No   | (0,34)    | Ranged attack, non-looping. |
| `attack_ranged_fast` | 7           | 33x33            | 8              | 0.01           | No   | (0,34)    | Faster ranged attack, non-looping. |