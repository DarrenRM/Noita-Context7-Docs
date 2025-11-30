---
title: Giant Enemy Sprite Animations
category: enemies_gfx
---

# Giant Enemy Sprite Animations

This document details the sprite animations for the "Giant" enemy in Noita, as defined in `data/enemies_gfx/giant.xml`. It focuses on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/giant.png` - The path to the sprite sheet.
*   **offset\_x**: `11.5` - Horizontal offset for sprite positioning.
*   **offset\_y**: `27` - Vertical offset for sprite positioning.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The file defines several distinct animations using `<RectAnimation>` tags. Each animation describes a sequence of frames from the sprite sheet.

### `stand` Animation

*   **name**: `stand`
*   **pos\_x**: `0` - Starting X coordinate on the sprite sheet.
*   **pos\_y**: `0` - Starting Y coordinate on the sprite sheet.
*   **frame\_count**: `6` - Total number of frames in the animation.
*   **frame\_width**: `23` - Width of each individual frame.
*   **frame\_height**: `32` - Height of each individual frame.
*   **frame\_wait**: `0.25` - Time in seconds between frames.
*   **frames\_per\_row**: `6` - Number of frames per row on the sprite sheet.
*   **loop**: `1` - Indicates the animation loops (1 for true, 0 for false).

### `walk` Animation

*   **name**: `walk`
*   **pos\_x**: `0`
*   **pos\_y**: `32`
*   **frame\_count**: `6`
*   **frame\_width**: `23`
*   **frame\_height**: `32`
*   **frame\_wait**: `0.18`
*   **frames\_per\_row**: `6`
*   **loop**: `1`
*   **Events**:
    *   `frame="0" name="step"`: Triggers a "step" event on the first frame.
    *   `frame="3" name="step"`: Triggers a "step" event on the fourth frame.

### `run` Animation

*   **name**: `run`
*   **pos\_x**: `0`
*   **pos\_y**: `32` (Copied from `walk`)
*   **frame\_count**: `6`
*   **frame\_width**: `23`
*   **frame\_height**: `32`
*   **frame\_wait**: `0.15` (Faster than `walk`)
*   **frames\_per\_row**: `8`
*   **loop**: `1`
*   **Events**:
    *   `frame="0" name="step"`
    *   `frame="3" name="step"`

### `burn` Animation

*   **name**: `burn`
*   **pos\_x**: `0`
*   **pos\_y**: `32` (Copied from `walk`)
*   **frame\_count**: `6`
*   **frame\_width**: `23`
*   **frame\_height**: `32`
*   **frame\_wait**: `0.15`
*   **frames\_per\_row**: `8`
*   **loop**: `1`
*   **Events**:
    *   `frame="0" name="step"`
    *   `frame="3" name="step"`

### `attack` Animation

*   **name**: `attack`
*   **pos\_x**: `0`
*   **pos\_y**: `64`
*   **frame\_count**: `6`
*   **frame\_width**: `23`
*   **frame\_height**: `32`
*   **frame\_wait**: `0.05` (Very fast)
*   **frames\_per\_row**: `9`
*   **loop**: `0` (Does not loop)
*   **Events**:
    *   `frame="4" name="hit"`: Triggers a "hit" event on the fifth frame.

### `attack_ranged` Animation

*   **name**: `attack_ranged`
*   **pos\_x**: `0`
*   **pos\_y**: `64`
*   **frame\_count**: `6`
*   **frame\_width**: `23`
*   **frame\_height**: `32`
*   **frame\_wait**: `0.12`
*   **frames\_per\_row**: `9`
*   **loop**: `0`
*   **Events**:
    *   `frame="4" name="throw"`: Triggers a "throw" event on the fifth frame.
    *   `frame="4" name="throw_release"`: Triggers a "throw\_release" event on the fifth frame.
    *   `frame="3" name="attack_shoot"`: Triggers an "attack\_shoot" event on the fourth frame.