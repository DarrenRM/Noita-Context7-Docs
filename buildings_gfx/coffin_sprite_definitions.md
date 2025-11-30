---
title: Coffin Sprite Definitions
category: data/buildings_gfx
---

# Coffin Sprite Definitions

This document details the sprite definitions for the Coffin building in Noita, focusing on its visual animations.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation for the coffin.

### Key Attributes:

*   **filename**: `data/buildings_gfx/coffin.png` - The path to the sprite sheet.
*   **offset\_x**: `8` - Horizontal offset for the sprite.
*   **offset\_y**: `19` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animations

The coffin has several distinct animations defined using `<RectAnimation>` tags.

### `stand` Animation

This is the default, idle animation for the coffin.

*   **name**: `"stand"`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `5`
*   **frame\_width**: `16`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.13` - Duration each frame is displayed.
*   **frames\_per\_row**: `6`
*   **loop**: `1` - Indicates the animation loops indefinitely.

### `opening` Animation

This animation plays when the coffin is opened.

*   **name**: `"opening"`
*   **pos\_x**: `0`
*   **pos\_y**: `20`
*   **frame\_count**: `6`
*   **frame\_width**: `16`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.1` - Faster than the stand animation.
*   **frames\_per\_row**: `6`
*   **loop**: `0` - This animation plays only once.
*   **next\_animation**: `"open"` - Transitions to the `open` animation after completion.

### `open` Animation

This is the state where the coffin is fully open.

*   **name**: `"open"`
*   **pos\_x**: `0`
*   **pos\_y**: `40`
*   **frame\_count**: `5`
*   **frame\_width**: `16`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.13`
*   **frames\_per\_row**: `6`
*   **loop**: `1` - The coffin remains open, looping this animation.

### `closing` Animation

This animation plays when the coffin is closing.

*   **name**: `"closing"`
*   **pos\_x**: `0`
*   **pos\_y**: `60`
*   **frame\_count**: `5`
*   **frame\_width**: `16`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.1` - Faster than the stand animation.
*   **frames\_per\_row**: `6`
*   **loop**: `0` - This animation plays only once.
*   **next\_animation**: `"stand"` - Transitions back to the `stand` animation after completion.