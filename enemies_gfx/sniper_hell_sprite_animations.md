---
title: Sniper Hell Sprite Animations
category: enemies_gfx
---

# Sniper Hell Sprite Animations

This document details the sprite animations for the "Sniper Hell" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/sniper_hell.png` - The path to the sprite sheet.
*   **offset\_x**: `5` - Horizontal offset for the sprite.
*   **offset\_y**: `14` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation played when the enemy is idle.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation.

### Animation Structure

Each `<RectAnimation>` defines a sequence of frames from the sprite sheet.

#### Key Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack\_ranged").
*   **frame\_count**: Total number of frames in the animation.
*   **frame\_width**: Width of each individual frame.
*   **frame\_height**: Height of each individual frame.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: Delay between frames in seconds.
*   **pos\_x**: X-coordinate of the top-left corner of the animation block on the sprite sheet.
*   **pos\_y**: Y-coordinate of the top-left corner of the animation block on the sprite sheet.
*   **loop**: `0` indicates the animation plays once; omitted or `1` implies looping.
*   **shrink\_by\_one\_pixel**: `1` indicates a slight shrinking effect applied to frames.

### Notable Animations and Events

#### `stand`
*   **frame\_count**: 12
*   **frame\_wait**: 0.15
*   **Events**:
    *   `breath` (frame 8): Triggers a "breath" event.

#### `walk`
*   **frame\_count**: 6
*   **frame\_wait**: 0.06
*   **Events**:
    *   `step` (frame 0): Triggers a "step" event.
    *   `step` (frame 3): Triggers another "step" event.

#### `run`
*   **frame\_count**: 6
*   **frame\_wait**: 0.05
*   **Events**:
    *   `step` (frame 0): Triggers a "step" event.
    *   `step` (frame 3): Triggers another "step" event.

#### `attack_ranged`
*   **frame\_count**: 13
*   **frame\_wait**: 0.07
*   **loop**: 0 (plays once)
*   **Events**:
    *   `shoot_sniper` (frame 8): Triggers the "shoot\_sniper" event, likely firing a projectile.

#### `attack`
*   **frame\_count**: 6
*   **frame\_wait**: 0.05
*   **loop**: 0 (plays once)
*   **Events**:
    *   `kick` (frame 3): Triggers a "kick" event.

#### `burn`
*   **frame\_count**: 6
*   **frame\_wait**: 0.04
*   **Events**:
    *   `step` (frame 0): Triggers a "step" event.
    *   `step` (frame 3): Triggers another "step" event.

#### `jump_up`
*   **frame\_count**: 3
*   **frame\_wait**: 0.05
*   **loop**: 0 (plays once)
*   **Events**:
    *   `jump` (frame 0): Triggers a "jump" event.

#### `jump_fall`
*   **frame\_count**: 3
*   **frame\_wait**: 0.05
*   **loop**: 0 (plays once)

#### `swim_idle`
*   **frame\_count**: 6
*   **frame\_wait**: 0.05
*   **Events**:
    *   `paddle` (frame 0): Triggers a "paddle" event.
    *   `paddle` (frame 3): Triggers another "paddle" event.

#### `swim_move`
*   **frame\_count**: 6
*   **frame\_wait**: 0.05
*   **Events**:
    *   `paddle` (frame 0): Triggers a "paddle" event.
    *   `paddle` (frame 3): Triggers another "paddle" event.

#### `attack_throw`
*   **frame\_count**: 6
*   **frame\_wait**: 0.05
*   **loop**: 0 (plays once)
*   **Events**:
    *   `throw` (frame 4): Triggers a "throw" event.

#### `jump_prepare`
*   **frame\_count**: 3
*   **frame\_wait**: 0.05
*   **loop**: 0 (plays once)
*   **Events**:
    *   `jump_start` (frame 3): Triggers a "jump\_start" event.

### Event Attributes

Each `<Event>` tag within an animation defines a specific action or trigger.

#### Key Attributes:

*   **name**: The identifier for the event (e.g., "breath", "step", "shoot\_sniper").
*   **frame**: The frame number at which the event occurs.
*   **probability**: The chance of the event occurring (1 means always).
*   **max\_distance**: Maximum distance for the event to be considered.
*   **check\_physics\_material**: `1` means the event checks the physics material of the ground; `0` means it does not.
*   **on\_finished**: `0` indicates the event does not affect animation playback.