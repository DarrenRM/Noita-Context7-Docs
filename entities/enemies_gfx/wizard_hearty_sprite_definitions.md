---
title: Wizard Hearty Sprite Definitions
category: entities/enemies_gfx
---

# Wizard Hearty Sprite Definitions

This document details the sprite and animation definitions for the "Wizard Hearty" enemy in Noita, as defined in the `wizard_hearty.xml` file. This file specifies the visual assets and their corresponding animations, including frame data, timing, and specific events triggered during animations.

## Core Sprite Properties

These are the primary attributes defining the sprite's visual representation and its relationship to the game world.

*   **`filename`**: `data/enemies_gfx/wizard_hearty.png`
    *   The main image file containing all frames for the wizard's animations.
*   **`hotspots_filename`**: `data/enemies_gfx/wizard_hotspots.png`
    *   An associated image file defining specific points of interest (hotspots) on the sprite, such as for collision or attachment points.
*   **`offset_x`**: `8`
    *   Horizontal offset applied to the sprite's position.
*   **`offset_y`**: `14`
    *   Vertical offset applied to the sprite's position.
*   **`default_animation`**: `"stand"`
    *   The animation that plays by default when the entity is idle.

## Animation Definitions

The `Sprite` element contains multiple `RectAnimation` elements, each defining a distinct animation.

### `stand` Animation

*   **`name`**: `"stand"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `19`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.1`
    *   Duration each frame is displayed before advancing.
*   **`pos_x`**: `0`
*   **`pos_y`**: `1`
    *   The starting coordinates within the sprite sheet for this animation's frames.

### `walk` Animation

*   **`name`**: `"walk"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `19`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.085`
*   **`pos_x`**: `0`
*   **`pos_y`**: `21`
    *   This animation's frames are located below the `stand` animation frames on the sprite sheet.
*   **Events**:
    *   **`step`**: Triggered at `frame="0"` and `frame="3"`. These events likely correspond to footstep sounds or particle effects.
        *   `check_physics_material="1"`: Checks the material of the ground the entity is standing on.
        *   `probability="1"`: Always triggers if conditions are met.

### `run` Animation

*   **`name`**: `"run"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `19`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.085`
*   **`pos_x`**: `0`
*   **`pos_y`**: `21`
    *   Shares the same sprite sheet coordinates as the `walk` animation.
*   **Events**:
    *   **`step`**: Triggered at `frame="0"` and `frame="3"`. Similar to the `walk` animation, these likely represent faster footstep cues.

### `burn` Animation

*   **`name`**: `"burn"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `16`
*   **`frame_height`**: `19`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.085`
*   **`pos_x`**: `0`
*   **`pos_y`**: `21`
    *   Also shares the same sprite sheet coordinates as `walk` and `run`.
*   **Events**:
    *   **`step`**: Triggered at `frame="0"` and `frame="3"`. These might be visual cues for burning or related effects.

### `attack_ranged` Animation

*   **`name`**: `"attack_ranged"`
*   **`frame_count`**: `7`
*   **`frame_width`**: `17`
*   **`frame_height`**: `20`
*   **`frames_per_row`**: `6`
*   **`frame_wait`**: `0.08`
*   **`pos_x`**: `0`
*   **`pos_y`**: `41`
*   **`shrink_by_one_pixel`**: `1`
    *   Indicates a slight shrinking of the sprite for this animation.
*   **Events**:
    *   **`shoot_magic`**: Triggered at `frame="5"`. This event is crucial for initiating the projectile firing action.
        *   `check_physics_material="0"`: Does not check the ground material.
        *   `probability="1"`: Always triggers when frame 5 is reached.

### `fly_idle` Animation

*   **`name`**: `"fly_idle"`
*   **`frame_count`**: `4`
*   **`frame_width`**: `17`
*   **`frame_height`**: `20`
*   **`frames_per_row`**: `15`
*   **`frame_wait`**: `0.12`
*   **`pos_x`**: `0`
*   **`pos_y`**: `81`
*   **`shrink_by_one_pixel`**: `1`

### `fly_move` Animation

*   **`name`**: `"fly_move"`
*   **`frame_count`**: `4`
*   **`frame_width`**: `17`
*   **`frame_height`**: `20`
*   **`frames_per_row`**: `15`
*   **`frame_wait`**: `0.12`
*   **`pos_x`**: `0`
*   **`pos_y`**: `101`
*   **`shrink_by_one_pixel`**: `1`

## Hotspots

*   **`Hotspot`**:
    *   **`name`**: `"cape"`
    *   **`color`**: `"ff"`
        *   Defines a hotspot named "cape" with a specific color value, likely used for visual effects or interactions related to the wizard's cape.