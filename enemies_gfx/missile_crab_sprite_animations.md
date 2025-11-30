---
title: Missile Crab Sprite Animations
category: enemies_gfx
---

# Missile Crab Sprite Animations

This document details the sprite animations for the Missile Crab enemy in Noita, as defined in its `missilecrab.xml` file. This information is crucial for modders looking to alter or create new animations for this entity.

## Sprite Definition

The main `<Sprite>` tag defines the base properties and the sprite sheet used for the Missile Crab.

### Key Attributes:

*   **filename**: `data/enemies_gfx/missilecrab.png` - Specifies the path to the sprite sheet image.
*   **offset\_x**: `10` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `16` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is idle.

## Animation Types

The Missile Crab utilizes several distinct animations, each defined by a `<RectAnimation>` tag. These animations control how the sprite sheet is interpreted to create movement and actions.

### Key Animation Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack\_ranged").
*   **pos\_x**: The starting X-coordinate on the sprite sheet for this animation's frames.
*   **pos\_y**: The starting Y-coordinate on the sprite sheet for this animation's frames.
*   **frame\_count**: The total number of frames in this animation.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **loop**: `1` for looping animations, `0` for non-looping animations.

### Defined Animations:

| Animation Name   | Sprite Sheet Y-Offset | Frame Count | Frame Size (WxH) | Frame Wait (s) | Looping | Key Events                                                              |
| :--------------- | :-------------------- | :---------- | :--------------- | :------------- | :------ | :---------------------------------------------------------------------- |
| **stand**        | `0`                   | 4           | 24x20            | 0.1            | Yes     | None                                                                    |
| **walk**         | `20`                  | 6           | 24x20            | 0.08           | Yes     | `step` (on frames 1 & 4)                                                |
| **run**          | `20`                  | 6           | 24x20            | 0.08           | Yes     | `step` (on frames 1 & 4) - *Copied from walk*                           |
| **burn**         | `20`                  | 6           | 24x20            | 0.08           | Yes     | `step` (on frames 1 & 4) - *Copied from walk*                           |
| **jump\_up**     | `40`                  | 4           | 24x20            | 0.09           | No      | `jump` (on frame 0)                                                     |
| **land**         | `60`                  | 2           | 24x20            | 0.082          | No      | `land` (on frame 0)                                                     |
| **attack\_ranged** | `80`                  | 8           | 24x20            | 0.12           | No      | `hatch` (on frame 3), `shoot_rocket` (on frame 5)                       |
| **alert**        | `100`                 | 3           | 24x20            | 0.09           | No      | `beep` (on frame 0)                                                     |
| **jump\_prepare**| `120`                 | 3           | 24x20            | 0.06           | No      | `jump_start` (on frame 3)                                               |
| **aim**          | `140`                 | 4           | 24x20            | 0.04           | Yes     | None                                                                    |

### Animation Events:

Events are triggered at specific frames within an animation.

*   **name**: The name of the event (e.g., "step", "jump", "shoot\_rocket").
*   **frame**: The frame number on which the event occurs.
*   **probability**: The chance of the event triggering (usually 1 for guaranteed events).
*   **check\_physics\_material**: If `1`, the event might be influenced by the material the entity is standing on.

This structured documentation allows AI tools to easily parse and understand the visual components of the Missile Crab, facilitating modifications to its appearance and behavior.