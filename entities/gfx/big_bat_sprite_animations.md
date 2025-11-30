---
title: Big Bat Sprite Animations
category: entities/gfx
---

# Big Bat Sprite Animations

This document details the sprite animations for the "Big Bat" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/bigbat.png` - Path to the sprite sheet.
*   **offset\_x**: `24` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `24` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `<RectAnimation>`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack\_ranged").
*   **frame\_count**: Total number of frames in the animation.
*   **frame\_height**: Height of each individual frame in pixels.
*   **frame\_width**: Width of each individual frame in pixels.
*   **frames\_per\_row**: Number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: Delay between frames in seconds.
*   **pos\_x**: X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates if frames should be shrunk by one pixel (often for visual consistency).
*   **loop**: `0` or `1` - Whether the animation should loop.

### Animation Types:

The Big Bat has several defined animations:

*   **stand**: Idle animation.
*   **walk**: Walking animation.
*   **run**: Running animation.
*   **burn**: Animation when burning.
*   **fly\_idle**: Idle animation while flying.
*   **fly\_move**: Animation while moving in the air.
*   **attack\_ranged**: Animation for ranged attacks.

## Event Definitions

Events can be triggered at specific frames within an animation.

### Key Attributes for `<Event>`:

*   **name**: The name of the event (e.g., "flap", "duplicate").
*   **frame**: The frame number (0-indexed) at which the event should trigger.
*   **probability**: The chance (0.0 to 1.0) that this event will trigger if the frame is reached.
*   **on\_finished**: `0` or `1` - Whether the event should trigger when the animation finishes.
*   **max\_distance**: Maximum distance for certain event types (e.g., physics checks).
*   **check\_physics\_material**: `0` or `1` - Whether to check the physics material at the event's location.

### Notable Events:

*   **flap**: Appears in most animations, likely related to wing movement.
*   **duplicate**: Occurs in the `attack_ranged` animation on frame 4, suggesting it might be related to spawning projectiles or a similar effect.