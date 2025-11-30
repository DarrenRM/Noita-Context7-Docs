---
title: Alchemist Sprite Animations
category: entities/gfx
---

# Alchemist Sprite Animations

This document details the sprite animations for the Alchemist enemy in Noita, as defined in `alchemist.xml`. It focuses on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its offset.

### Key Attributes:

*   **filename**: `data/enemies_gfx/alchemist.png` - The path to the sprite sheet.
*   **offset\_x**: `9` - Horizontal offset for the sprite.
*   **offset\_y**: `15` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `<RectAnimation>`:

*   **name**: The identifier for the animation (e.g., "stand", "attack", "walk").
*   **frame\_count**: Total number of frames in the animation.
*   **frame\_width**: Width of a single frame in pixels.
*   **frame\_height**: Height of a single frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: Delay between frames in seconds.
*   **pos\_x**: X-coordinate of the top-left corner of the animation frames on the sprite sheet.
*   **pos\_y**: Y-coordinate of the top-left corner of the animation frames on the sprite sheet.
*   **loop**: `0` indicates the animation does not loop (plays once), otherwise it loops.

### Notable Animations and Events:

#### `stand`

*   **frame\_count**: 6
*   **frame\_wait**: 0.2
*   **pos\_y**: 0

#### `attack`

*   **frame\_count**: 6
*   **frame\_wait**: 0.05
*   **loop**: 0 (plays once)
*   **pos\_y**: 95
*   **Events**:
    *   `hit` (frame 4): Triggers when the attack connects.
    *   `voc_attack` (frame 4): Triggers a vocalization for the attack.

#### `attack_ranged`

*   **frame\_count**: 6
*   **frame\_wait**: 0.09
*   **loop**: 0 (plays once)
*   **pos\_y**: 95
*   **Events**:
    *   `throw_release` (frame 4): Triggers the projectile release.
    *   `throw` (frame 4): General throw action trigger.

#### `walk`

*   **frame\_count**: 6
*   **frame\_wait**: 0.12
*   **pos\_y**: 19
*   **Events**:
    *   `step` (frame 2 & 5): Triggers footstep sounds/effects.

#### `run`

*   **frame\_count**: 6
*   **frame\_wait**: 0.12
*   **pos\_y**: 19
*   **Events**:
    *   `step` (frame 2 & 5): Triggers footstep sounds/effects.

#### `jump_up`

*   **frame\_count**: 3
*   **frame\_wait**: 0.09
*   **loop**: 0 (plays once)
*   **pos\_y**: 38
*   **Events**:
    *   `jump` (frame 0): Triggers the jump action.

#### `jump_fall`

*   **frame\_count**: 3
*   **frame\_wait**: 0.09
*   **loop**: 0 (plays once)
*   **pos\_y**: 57

#### `land`

*   **frame\_count**: 2
*   **frame\_wait**: 0.08
*   **loop**: 0 (plays once)
*   **pos\_y**: 76
*   **Events**:
    *   `land` (frame 0): Triggers the landing action.

#### `burn`

*   **frame\_count**: 6
*   **frame\_wait**: 0.1
*   **pos\_y**: 114
*   **Events**:
    *   `step` (frame 2 & 5): Triggers effects during burning.

#### `swim_idle`

*   **frame\_count**: 6
*   **frame\_wait**: 0.085
*   **pos\_y**: 19
*   **Events**:
    *   `paddle` (frame 2 & 5): Triggers swimming paddle actions.

#### `swim_move`

*   **frame\_count**: 6
*   **frame\_wait**: 0.08
*   **pos\_y**: 19
*   **Events**:
    *   `paddle` (frame 2 & 5): Triggers swimming paddle actions.

#### `jump_prepare`

*   **frame\_count**: 2
*   **frame\_wait**: 0.09
*   **loop**: 0 (plays once)
*   **pos\_y**: 133
*   **Events**:
    *   `voc_jump` (frame 0): Triggers a vocalization before jumping.
    *   `jump_start` (frame 2): Triggers the start of the jump animation.

### Event Attributes for `<Event>`:

*   **name**: The name of the event (e.g., "hit", "step", "jump").
*   **frame**: The frame number within the animation when the event occurs.
*   **probability**: Likelihood of the event triggering (usually 1).
*   **max\_distance**: Maximum distance for the event to be considered (often 500).
*   **check\_physics\_material**: `1` if the event depends on the physics material of the ground, `0` otherwise.
*   **on\_finished**: `0` indicates the event does not affect animation completion.