---
title: Fly Enemy Graphics
category: entities
---

# Fly Enemy Graphics

This document details the graphical assets and animations for the "Fly" enemy in Noita, intended for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the overall graphical properties and default animation for the fly enemy.

### Key Attributes:

*   **`default_animation`**: Specifies the animation to play by default. In this case, it's set to `"fly_move"`. Note that it's also defined as `"stand"` later, which might indicate an override or a potential point of confusion for modders.
*   **`filename`**: The path to the sprite sheet image file (`data/enemies_gfx/fly.png`).
*   **`offset_x`**: Horizontal offset for the sprite's origin (10 pixels).
*   **`offset_y`**: Vertical offset for the sprite's origin (15 pixels).

## RectAnimation Definitions

Multiple `<RectAnimation>` tags define distinct animations for the fly enemy. Each animation is composed of frames from the sprite sheet.

### Animations:

| Animation Name | Frame Count | Frame Dimensions (Width x Height) | Frame Wait (sec) | Frames Per Row | Sprite Sheet Position (X, Y) | Notes