---
title: Torch Stand Emissive Sprite
category: props_gfx
---

# Torch Stand Emissive Sprite

This document describes the sprite data for an emissive torch stand, commonly used in Noita. It defines the visual appearance and animation frames for this prop.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/props_gfx/torch_stand_emissive.png` - The path to the sprite sheet containing all animation frames.
*   **offset\_x**: `6` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `18` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"default"` - Specifies the animation to play by default when the sprite is loaded.

## Animations

The `<Sprite>` tag contains one or more `<RectAnimation>` tags, each defining a distinct animation sequence.

### Animation: `default`

This animation represents the active, lit state of the torch stand.

#### Key Attributes:

*   **name**: `"default"` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X coordinate on the sprite sheet for this animation's frames.
*   **pos\_y**: `0` - The starting Y coordinate on the sprite sheet for this animation's frames.
*   **frame\_count**: `4` - The total number of frames in this animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `19` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` - Indicates that the animation should loop continuously.

### Animation: `out`

This animation likely represents the torch stand when it is unlit or in a deactivated state.

#### Key Attributes:

*   **name**: `"out"` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X coordinate on the sprite sheet for this animation's frames.
*   **pos\_y**: `19` - The starting Y coordinate on the sprite sheet for this animation's frames. This indicates the frames for this animation are located below the `default` animation frames.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `19` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously.