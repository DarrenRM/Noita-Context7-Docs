---
title: Miniblob Emissive Sprite Animations
category: entities
---

# Miniblob Emissive Sprite Animations

This document details the sprite animations for the Miniblob enemy, specifically its emissive graphical representation. It outlines the primary sprite sheet and the various animations defined within it.

## Sprite Definition

The main sprite definition for the Miniblob's emissive form.

### Key Attributes:

*   **filename**: `data/enemies_gfx/miniblob_emissive.png` - The path to the sprite sheet image.
*   **offset\_x**: `7` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `13` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animations

This section describes the different animations available for the Miniblob, including their frame details and timing.

### `stand` Animation

The default idle animation for the Miniblob.

*   **name**: `stand`
*   **frame\_count**: `6`
*   **frame\_width**: `15`
*   **frame\_height**: `17`
*   **frames\_per\_row**: `8`
*   **frame\_wait**: `0.16` (seconds per frame)
*   **pos\_x**: `0` (starting X position on sprite sheet)
*   **pos\_y**: `1` (starting Y position on sprite sheet)
*   **shrink\_by\_one\_pixel**: `1` (indicates frames are 1 pixel smaller than their defined dimensions)

### `attack` Animation

The animation played when the Miniblob attacks.

*   **name**: `attack`
*   **frame\_count**: `3`
*   **frame\_width**: `21`
*   **frame\_height**: `17`
*   **frames\_per\_row**: `8`
*   **frame\_wait**: `0.064` (seconds per frame)
*   **loop**: `0` (animation does not loop)
*   **pos\_x**: `0`
*   **pos\_y**: `1`
*   **shrink\_by\_one\_pixel**: `1`

### `walk` Animation

The animation for the Miniblob when it is walking.

*   **name**: `walk`
*   **frame\_count**: `5`
*   **frame\_width**: `14`
*   **frame\_height**: `16`
*   **frames\_per\_row**: `8`
*   **frame\_wait**: `0.1` (seconds per frame)
*   **pos\_x**: `0`
*   **pos\_y**: `18`
*   **shrink\_by\_one\_pixel**: `1` (implied, as it shares properties with other animations that have it)

### `run` Animation

The animation for the Miniblob when it is running.

*   **name**: `run`
*   **frame\_count**: `5`
*   **frame\_width**: `14`
*   **frame\_height**: `16`
*   **frames\_per\_row**: `8`
*   **frame\_wait**: `0.1` (seconds per frame)
*   **pos\_x**: `0`
*   **pos\_y**: `18`
*   **shrink\_by\_one\_pixel**: `1` (implied)

### `burn` Animation

The animation for the Miniblob when it is burning.

*   **name**: `burn`
*   **frame\_count**: `5`
*   **frame\_width**: `14`
*   **frame\_height**: `16`
*   **frames\_per\_row**: `8`
*   **frame\_wait**: `0.1` (seconds per frame)
*   **pos\_x**: `0`
*   **pos\_y**: `18`
*   **shrink\_by\_one\_pixel**: `1` (implied)

### `jump_up` Animation

The animation for the Miniblob when it jumps upwards.

*   **name**: `jump_up`
*   **frame\_count**: `1`
*   **frame\_width**: `14`
*   **frame\_height**: `16`
*   **frames\_per\_row**: `8`
*   **frame\_wait**: `0.082` (seconds per frame)
*   **loop**: `0` (animation does not loop)
*   **pos\_x**: `0`
*   **pos\_y**: `18`
*   **shrink\_by\_one\_pixel**: `1` (implied)

### `jump_fall` Animation

The animation for the Miniblob when it is falling after a jump.

*   **name**: `jump_fall`
*   **frame\_count**: `1`
*   **frame\_width**: `14`
*   **frame\_height**: `16`
*   **frames\_per\_row**: `8`
*   **frame\_wait**: `0.082` (seconds per frame)
*   **loop**: `0` (animation does not loop)
*   **pos\_x**: `28` (starting X position on sprite sheet)
*   **pos\_y**: `18`
*   **shrink\_by\_one\_pixel**: `1` (implied)