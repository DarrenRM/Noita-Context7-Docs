---
title: Scorpion Sprite Animations
category: entities/enemies_gfx
---

# Scorpion Sprite Animations

This document details the sprite animations for the Scorpion enemy in Noita, as defined in `scorpion.xml`. It focuses on the key attributes of each animation state.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its offset.

### Key Attributes:

*   **filename**: `data/enemies_gfx/scorpion.png` - The path to the sprite sheet.
*   **offset\_x**: `5` - Horizontal offset for the sprite.
*   **offset\_y**: `3` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation state that plays by default.

## Animations

The Scorpion has several defined animation states, each using `<RectAnimation>` to define its frames.

### `stand` Animation

This is the default idle animation for the Scorpion.

#### Key Attributes:

*   **name**: `"stand"`
*   **pos\_x**: `0` - Starting X coordinate on the sprite sheet.
*   **pos\_y**: `0` - Starting Y coordinate on the sprite sheet.
*   **frame\_count**: `1` - Number of frames in this animation.
*   **frame\_width**: `10` - Width of each frame.
*   **frame\_height**: `7` - Height of each frame.
*   **frame\_wait**: `0.23` - Duration each frame is displayed.
*   **frames\_per\_row**: `6` - How many frames are in a single row of the sprite sheet.
*   **loop**: `1` - Whether the animation should loop (1 for true).

### `walk` Animation

This animation is used for the Scorpion's walking movement.

#### Key Attributes:

*   **name**: `"walk"`
*   **pos\_x**: `0`
*   **pos\_y**: `7` - Starts on the second row of the sprite sheet.
*   **frame\_count**: `4` - Number of frames for walking.
*   **frame\_width**: `10`
*   **frame\_height**: `7`
*   **frame\_wait**: `0.1` - Faster frame duration than `stand`.
*   **frames\_per\_row**: `6`
*   **loop**: `1`

#### Events:

*   **frame `1`**: `step` event with `probability="0.7"` and `check_physics_material="1"`.
*   **frame `3`**: `step` event with `probability="0.7"` and `check_physics_material="1"`.
    These events likely trigger footstep sounds or particle effects.

### `run` Animation

This animation is a direct copy of the `walk` animation.

#### Key Attributes:

*   **name**: `"run"`
*   **pos\_x**: `0`
*   **pos\_y**: `7`
*   **frame\_count**: `4`
*   **frame\_width**: `10`
*   **frame\_height**: `7`
*   **frame\_wait**: `0.1`
*   **frames\_per\_row**: `6`
*   **loop**: `1`

#### Events:

*   **frame `1`**: `step` event with `probability="0.7"` and `check_physics_material="1"`.
*   **frame `3`**: `step` event with `probability="0.7"` and `check_physics_material="1"`.

### `burn` Animation

This animation is also a direct copy of the `walk` animation.

#### Key Attributes:

*   **name**: `"burn"`
*   **pos\_x**: `0`
*   **pos\_y**: `7`
*   **frame\_count**: `4`
*   **frame\_width**: `10`
*   **frame\_height**: `7`
*   **frame\_wait**: `0.1`
*   **frames\_per\_row**: `6`
*   **loop**: `1`

#### Events:

*   **frame `1`**: `step` event with `probability="0.7"` and `check_physics_material="1"`.
*   **frame `3`**: `step` event with `probability="0.7"` and `check_physics_material="1"`.