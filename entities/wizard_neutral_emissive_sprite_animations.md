---
title: Wizard Neutral Emissive Sprite Animations
category: entities
---

# Wizard Neutral Emissive Sprite Animations

This document details the sprite animations for the "wizard_neutral_emissive" entity in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/wizard_neutral_emissive.png` - The path to the sprite sheet.
*   **offset\_x**: `8` - Horizontal offset for the sprite.
*   **offset\_y**: `14` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The `<RectAnimation>` tags define individual animations for the sprite.

### Common Attributes:

*   **name**: The name of the animation (e.g., "stand", "walk", "attack\_ranged").
*   **frame\_count**: Total number of frames in the animation.
*   **frame\_width**: Width of each frame in pixels.
*   **frame\_height**: Height of each frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: Delay between frames in seconds.
*   **pos\_x**: X-coordinate of the animation's starting position on the sprite sheet.
*   **pos\_y**: Y-coordinate of the animation's starting position on the sprite sheet.
*   **loop**: `0` indicates the animation does not loop (default is 1, which loops).
*   **shrink\_by\_one\_pixel**: `1` indicates the sprite is shrunk by one pixel (used for some animations).

### Defined Animations:

| Animation Name   | Frame Count | Frame Size (WxH) | Frames Per Row | Frame Wait (s) | Pos (X, Y) | Loop | Shrink | Key Events                               |
| :--------------- | :---------- | :--------------- | :------------- | :------------- | :--------- | :--- | :----- | :--------------------------------------- |
| **stand**        | 6           | 16x19            | 6              | 0.1            | (0, 1)     | 1    | 0      | None                                     |
| **walk**         | 6           | 16x19            | 6              | 0.085          | (0, 21)    | 1    | 0      | `step` at frame 0 and 3                  |
| **run**          | 6           | 16x19            | 6              | 0.085          | (0, 21)    | 1    | 0      | `step` at frame 0 and 3                  |
| **burn**         | 6           | 16x19            | 6              | 0.085          | (0, 21)    | 1    | 0      | `step` at frame 0 and 3                  |
| **attack\_ranged** | 7           | 17x20            | 6              | 0.05           | (0, 41)    | 0    | 1      | `shoot_magic` at frame 5                 |
| **fly\_idle**    | 4           | 17x20            | 15             | 0.12           | (0, 81)    | 1    | 1      | None                                     |
| **fly\_move**    | 4           | 17x20            | 15             | 0.12           | (0, 101)   | 1    | 1      | None                                     |

## Animation Events

Events trigger specific actions during an animation.

### Key Event Attributes:

*   **name**: The name of the event (e.g., "step", "shoot\_magic").
*   **frame**: The frame number at which the event occurs.
*   **probability**: The chance of the event firing (1 is 100%).
*   **on\_finished**: `0` means the event does not stop the animation.
*   **check\_physics\_material**: `1` means the event checks for physics materials (e.g., for footstep sounds).
*   **max\_distance**: Maximum distance for physics material checks.

### Notable Events:

*   **walk, run, burn**: Both have a `step` event at frame 0 and frame 3, likely for triggering footstep sounds or effects.
*   **attack\_ranged**: Has a `shoot_magic` event at frame 5, indicating the point where the projectile is fired.

## Hotspots

Hotspots define specific points on the sprite, often used for attaching other elements or defining interaction areas.

### Defined Hotspots:

*   **cape**:
    *   **color**: `ff` (likely represents a color or tag for the hotspot).