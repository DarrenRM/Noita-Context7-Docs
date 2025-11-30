---
title: Statue Sprite Animations
category: enemies_gfx
---

# Statue Sprite Animations

This document details the sprite animations for the "statue" enemy in Noita, as defined in `statue.xml`. It focuses on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/statue.png` - The path to the sprite sheet.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `14` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Common Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The horizontal starting position of the animation frames on the sprite sheet.
*   **pos\_y**: The vertical starting position of the animation frames on the sprite sheet.
*   **loop**: `0` indicates the animation does not loop (e.g., for one-off actions like jumping or attacking). Defaults to looping if not specified.

### Notable Animations:

| Animation Name | Frame Count | Frame Wait (s) | Loop | Y Position | Key Events                               |
| :------------- | :---------- | :------------- | :--- | :--------- | :--------------------------------------- |
| `stand`        | 6           | 0.2            | Yes  | 0          | None                                     |
| `walk`         | 6           | 0.105          | Yes  | 20         | `step` (at frames 0 and 3)               |
| `run`          | 6           | 0.105          | Yes  | 20         | `step` (at frames 0 and 3)               |
| `burn`         | 6           | 0.095          | Yes  | 20         | None                                     |
| `jump_up`      | 3           | 0.082          | No   | 40         | `jump` (at frame 0)                      |
| `jump_fall`    | 3           | 0.082          | No   | 60         | None                                     |
| `land`         | 3           | 0.075          | No   | 80         | `land` (at frame 0)                      |
| `fly_idle`     | 4           | 0.09           | Yes  | 100        | None                                     |
| `fly_move`     | 4           | 0.12           | Yes  | 120        | None                                     |
| `attack`       | 6           | 0.11           | No   | 140        | `attack_melee` (at frame 3)              |

## Animation Events

Events are triggered at specific frames within an animation.

### Common Event Attributes:

*   **name**: The name of the event (e.g., "step", "jump", "land", "attack\_melee").
*   **frame**: The frame number at which the event occurs.
*   **probability**: The likelihood of the event triggering (usually 1).
*   **on\_finished**: If `0`, the event does not stop the animation.
*   **check\_physics\_material**: If `1`, the game checks the physics material of the ground/surface for event context.
*   **max\_distance**: Maximum distance for certain event checks (e.g., `step`, `land`).

### Key Events:

*   **`step`**: Triggered during `walk` and `run` animations. Used for footstep sounds or effects.
*   **`jump`**: Triggered during `jump_up`. Signals the start of a jump.
*   **`land`**: Triggered during `land`. Signals the completion of a jump or fall.
*   **`attack_melee`**: Triggered during the `attack` animation. Indicates the moment of a melee attack.