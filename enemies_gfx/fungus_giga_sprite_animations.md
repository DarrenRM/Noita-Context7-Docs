---
title: Fungus Giga Sprite Animations
category: enemies_gfx
---

# Fungus Giga Sprite Animations

This document details the sprite animations for the Fungus Giga enemy in Noita, focusing on key attributes for modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

*   **filename**: `data/enemies_gfx/fungus_giga.png` - The texture file for the sprite.
*   **offset\_x**: `12` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `37` - Vertical offset of the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The `<RectAnimation>` tags define individual animations. Each animation consists of a sequence of frames.

### Stand Animation

*   **name**: `"stand"`
*   **frame\_count**: `6`
*   **frame\_width**: `24`
*   **frame\_height**: `42`
*   **frame\_wait**: `0.18` - Delay between frames in seconds.
*   **frames\_per\_row**: `8` - How many frames are in a single row of the sprite sheet.
*   **pos\_x**: `0` - Starting X position of the animation frames on the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames on the sprite sheet.

### Walk Animation

*   **name**: `"walk"`
*   **frame\_count**: `6`
*   **frame\_width**: `24`
*   **frame\_height**: `42`
*   **frame\_wait**: `0.16`
*   **frames\_per\_row**: `6`
*   **pos\_x**: `0`
*   **pos\_y**: `42`
*   **Events**:
    *   `step` event at frame `0` and `3`. These likely trigger footstep sounds or particle effects.

### Run Animation

*   **name**: `"run"`
*   **frame\_count**: `6`
*   **frame\_width**: `24`
*   **frame\_height**: `42`
*   **frame\_wait**: `0.14`
*   **frames\_per\_row**: `6`
*   **pos\_x**: `0`
*   **pos\_y**: `42`
*   **Events**:
    *   `step` event at frame `0` and `3`.

### Burn Animation

*   **name**: `"burn"`
*   **frame\_count**: `6`
*   **frame\_width**: `24`
*   **frame\_height**: `42`
*   **frame\_wait**: `0.14`
*   **frames\_per\_row**: `6`
*   **pos\_x**: `0`
*   **pos\_y**: `42`
*   **Events**:
    *   `step` event at frame `0` and `3`.

### Jump Up Animation

*   **name**: `"jump_up"`
*   **frame\_count**: `1`
*   **frame\_width**: `24`
*   **frame\_height**: `42`
*   **frame\_wait**: `0.2`
*   **frames\_per\_row**: `8`
*   **pos\_x**: `24`
*   **pos\_y**: `42`
*   **Events**:
    *   `jump` event at frame `0`.

### Jump Fall Animation

*   **name**: `"jump_fall"`
*   **frame\_count**: `1`
*   **frame\_width**: `24`
*   **frame\_height**: `42`
*   **frame\_wait**: `0.2`
*   **frames\_per\_row**: `8`
*   **pos\_x**: `48`
*   **pos\_y**: `42`

## Key Modding Attributes

*   **frame\_wait**: Adjusting this value directly controls the speed of an animation. Lower values make it faster, higher values make it slower.
*   **frame\_count**: Changing this can alter the number of frames used in an animation, potentially requiring adjustments to the sprite sheet layout or `frames_per_row`.
*   **pos\_x / pos\_y**: These define the starting coordinates of the animation frames on the sprite sheet. Crucial for correctly mapping animations if the sprite sheet is modified.
*   **Events**: These are points within an animation where specific game actions or effects can be triggered (e.g., sounds, particle effects, damage). Modifying the `frame` or `name` of an event can change when and what happens during an animation.