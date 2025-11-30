---
title: Player Ghost Sprite Definitions
category: entities_gfx
---

# Player Ghost Sprite Definitions

This document details the sprite and animation definitions for the player ghost entity in Noita. It outlines the primary sprite sheet, animation sequences, and key event triggers.

## Sprite Definition

The main sprite for the player ghost is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/playerghost.png` - Path to the sprite texture file.
*   **hotspots_filename**: `data/enemies_gfx/player_hotspots.png` - Path to the sprite's hotspot definition file.
*   **offset_x**: `6` - Horizontal offset for the sprite.
*   **offset_y**: `6.5` - Vertical offset for the sprite.
*   **default_animation**: `"stand"` - The animation to play by default.

## Animation Sequences

The player ghost utilizes several `RectAnimation` tags to define different movement and action states. Each animation is a sequence of frames extracted from the sprite sheet.

### Key Animation Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **pos\_x**: The starting X coordinate of the animation frames on the sprite sheet.
*   **pos\_y**: The starting Y coordinate of the animation frames on the sprite sheet.
*   **shrink\_by\_one\_pixel**: A boolean indicating if frames should be shrunk by one pixel (often used for subtle effects).
*   **loop**: If set to `0`, the animation will not loop.

### Defined Animations:

| Name       | Frame Count | Frame Height | Frame Width | Frame Wait | Frames Per Row | Pos X | Pos Y | Loop |
| :--------- | :---------- | :----------- | :---------- | :--------- | :------------- | :---- | :---- | :--- |
| `stand`    | 6           | 20           | 13          | 0.2        | 8              | 0     | 1     | Yes  |
| `walk`     | 6           | 20           | 13          | 0.105      | 8              | 0     | 1     | Yes  |
| `run`      | 6           | 20           | 13          | 0.105      | 8              | 0     | 1     | Yes  |
| `burn`     | 6           | 20           | 13          | 0.095      | 8              | 0     | 1     | Yes  |
| `fly_move` | 4           | 20           | 13          | 0.09       | 8              | 0     | 21    | Yes  |
| `fly_idle` | 4           | 20           | 13          | 0.12       | 8              | 0     | 41    | Yes  |
| `attack`   | 6           | 20           | 13          | 0.08       | 8              | 0     | 61    | No   |

## Animation Events

Specific events can be triggered at certain frames within an animation.

### Key Event Attributes:

*   **name**: The name of the event (e.g., "step", "kick").
*   **frame**: The frame number (0-indexed) at which the event should trigger.
*   **probability**: The chance (0 to 1) that the event will trigger.
*   **max\_distance**: Maximum distance for certain event types (e.g., sound propagation).
*   **check\_physics\_material**: Whether to check the physics material at the event location.
*   **on\_finished**: If set to `1`, the event triggers when the animation finishes.

### Defined Events:

*   **Animation**: `walk`
    *   **Event Name**: `step`
    *   **Frame**: `2`
    *   **Probability**: `1`
*   **Animation**: `attack`
    *   **Event Name**: `kick`
    *   **Frame**: `3`
    *   **Probability**: `1`

## Hotspots

Hotspots define specific points of interest on the sprite, often used for attaching items or determining interaction points.

### Defined Hotspots:

*   **name**: `hand`
    *   **color**: `ff0000` (Red)
*   **name**: `belt`
    *   **color**: `ff00` (Green)
*   **name**: `cape`
    *   **color**: `ff` (Blue)