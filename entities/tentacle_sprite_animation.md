---
title: Tentacle Sprite Animation
category: entities
---

# Tentacle Sprite Animation

This document describes the sprite animation for the Tentacle entity in Noita.

## Sprite Definition

The main `<Sprite>` element defines the visual representation and default animation for the tentacle.

### Key Attributes:

*   **filename**: `data/entities/animals/parallel/tentacles/sprite.png` - The path to the sprite sheet.
*   **offset\_x**: `22.5` - Horizontal offset for the sprite.
*   **offset\_y**: `24.5` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

### Stand Animation

The `stand` animation defines the idle state of the tentacle.

#### Key Attributes:

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `"0"` - Starting X position on the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position on the sprite sheet.
*   **frame\_count**: `"4"` - The total number of frames in this animation.
*   **frame\_width**: `"45"` - The width of each individual frame.
*   **frame\_height**: `"49"` - The height of each individual frame.
*   **frame\_wait**: `"0.12"` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `"4"` - The number of frames in each row of the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop (1 for true, 0 for false).