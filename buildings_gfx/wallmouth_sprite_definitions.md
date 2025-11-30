---
title: Wallmouth Sprite Definitions
category: data/buildings_gfx
---

# Wallmouth Sprite Definitions

This document details the sprite definitions for the "wallmouth" building in Noita, focusing on its graphical animations.

## Sprite Element

The main `<Sprite>` element defines the base image and default animation for the wallmouth.

### Key Attributes:

*   **filename**: `data/buildings_gfx/wallmouth.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `12` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `8` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is idle.

## RectAnimation Elements

These elements define specific animations for the wallmouth.

### `stand` Animation

This animation represents the wallmouth in its idle state.

*   **name**: `"stand"`
*   **frame\_count**: `1` - Number of frames in this animation.
*   **frame\_width**: `24` - Width of each frame.
*   **frame\_height**: `16` - Height of each frame.
*   **frames\_per\_row**: `7` - Number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.1` - Duration (in seconds) each frame is displayed.
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.

### `attack` Animation

This animation defines the wallmouth's attack sequence.

*   **name**: `"attack"`
*   **frame\_count**: `7` - Number of frames in this animation.
*   **frame\_width**: `24` - Width of each frame.
*   **frame\_height**: `16` - Height of each frame.
*   **frames\_per\_row**: `7` - Number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.08` - Duration (in seconds) each frame is displayed.
*   **next\_animation**: `"stand"` - The animation to transition to after this one completes.
*   **loop**: `0` - Indicates that this animation does not loop.
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `16` - Y-coordinate of the animation's starting position within the sprite sheet.

### `yawn` Animation

This animation defines the wallmouth's yawning sequence.

*   **name**: `"yawn"`
*   **frame\_count**: `7` - Number of frames in this animation.
*   **frame\_width**: `24` - Width of each frame.
*   **frame\_height**: `16` - Height of each frame.
*   **frames\_per\_row**: `7` - Number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.1` - Duration (in seconds) each frame is displayed.
*   **next\_animation**: `"stand"` - The animation to transition to after this one completes.
*   **loop**: `0` - Indicates that this animation does not loop.
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `32` - Y-coordinate of the animation's starting position within the sprite sheet.