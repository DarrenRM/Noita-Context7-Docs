---
title: Elk Sprite Animations
category: enemies_gfx
---

# Elk Sprite Animations

This document details the sprite animations for the "Elk" enemy in Noita, as defined in `elk.xml`. It focuses on the key attributes of each animation, providing a concise overview for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its offsets.

### Key Attributes:

*   **filename**: `data/enemies_gfx/elk.png` - The path to the sprite sheet.
*   **offset\_x**: `16` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `18` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animations

The following `<RectAnimation>` tags define the different animations available for the Elk.

### `stand` Animation

*   **name**: `stand`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `1` - Number of frames in this animation.
*   **frame\_width**: `32` - Width of each frame.
*   **frame\_height**: `32` - Height of each frame.
*   **frame\_wait**: `0.2` - Time in seconds between frames.
*   **frames\_per\_row**: `10` - How many frames are in a single row of the sprite sheet.
*   **loop**: `1` - Whether the animation should loop (1 for yes, 0 for no).

### `walk` Animation

*   **name**: `walk`
*   **pos\_x**: `0`
*   **pos\_y**: `32` - This animation starts on the second row of the sprite sheet.
*   **frame\_count**: `6`
*   **frame\_width**: `32`
*   **frame\_height**: `32`
*   **frame\_wait**: `0.1`
*   **frames\_per\_row**: `10`
*   **loop**: `1`

#### Events:

*   **frame `0`**: `step` (probability `1`, `check_physics_material="1"`) - Triggers a "step" sound/event.
*   **frame `3`**: `step` (probability `1`, `check_physics_material="1"`) - Triggers another "step" sound/event.

### `look_around` Animation

*   **name**: `look_around`
*   **pos\_x**: `0`
*   **pos\_y**: `64` - This animation starts on the third row of the sprite sheet.
*   **frame\_count**: `10`
*   **frame\_width**: `32`
*   **frame\_height**: `32`
*   **frame\_wait**: `0.15`
*   **frames\_per\_row**: `10`
*   **loop**: `0` - This animation does not loop.

### `swim_idle` Animation

*   **name**: `swim_idle`
*   **pos\_x**: `0`
*   **pos\_y**: `96` - This animation starts on the fourth row of the sprite sheet.
*   **frame\_count**: `6`
*   **frame\_width**: `32`
*   **frame\_height**: `32`
*   **frame\_wait**: `0.13`
*   **frames\_per\_row**: `10`
*   **loop**: `1`

#### Events:

*   **frame `2`**: `paddle` (probability `1`, `check_physics_material="0"`) - Triggers a "paddle" sound/event.
*   **frame `5`**: `paddle` (probability `1`, `check_physics_material="0"`) - Triggers another "paddle" sound/event.

### `swim_move` Animation

*   **name**: `swim_move`
*   **pos\_x**: `0`
*   **pos\_y**: `96` - Shares the same sprite sheet row as `swim_idle`.
*   **frame\_count**: `6`
*   **frame\_width**: `32`
*   **frame\_height**: `32`
*   **frame\_wait**: `0.13`
*   **frames\_per\_row**: `10`
*   **loop**: `1`

#### Events:

*   **frame `2`**: `paddle` (probability `1`, `check_physics_material="0"`) - Triggers a "paddle" sound/event.
*   **frame `5`**: `paddle` (probability `1`, `check_physics_material="0"`) - Triggers another "paddle" sound/event.