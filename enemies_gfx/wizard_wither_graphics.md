---
title: Wizard Wither Graphics
category: enemies_gfx
---

# Wizard Wither Graphics

This document details the graphical assets and animations for the "Wizard Wither" enemy in Noita, intended for AI-assisted modding.

## Sprite Definition

The main sprite definition for the Wizard Wither.

### Key Attributes:

*   **`default_animation`**: `stand` - The animation played by default.
*   **`filename`**: `data/enemies_gfx/wizard_wither.png` - The primary image file for the sprite.
*   **`hotspots_filename`**: `data/enemies_gfx/wizard_hotspots.png` - The image file containing collision and interaction points.
*   **`offset_x`**: `8` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `14` - Vertical offset for the sprite's origin.

## Animations

This section describes the various animations defined for the Wizard Wither.

### `stand` Animation

The idle animation for the wizard.

*   **`frame_count`**: `6`
*   **`frame_height`**: `19`
*   **`frame_wait`**: `0.1`
*   **`frame_width`**: `16`
*   **`frames_per_row`**: `6`
*   **`pos_x`**: `0`
*   **`pos_y`**: `1`

### `walk` Animation

The animation for when the wizard is walking.

*   **`frame_count`**: `6`
*   **`frame_height`**: `19`
*   **`frame_wait`**: `0.085`
*   **`frame_width`**: `16`
*   **`frames_per_row`**: `6`
*   **`pos_x`**: `0`
*   **`pos_y`**: `21`

#### Events within `walk`:

*   **`step`**: Triggered at `frame="0"` and `frame="3"`.
    *   `check_physics_material="1"`: Checks for physics materials.
    *   `max_distance="500"`: Maximum distance for the event check.
    *   `probability="1"`: Always triggers when conditions are met.

### `run` Animation

The animation for when the wizard is running. Similar to `walk` in frame layout and events.

*   **`frame_count`**: `6`
*   **`frame_height`**: `19`
*   **`frame_wait`**: `0.085`
*   **`frame_width`**: `16`
*   **`frames_per_row`**: `6`
*   **`pos_x`**: `0`
*   **`pos_y`**: `21`

#### Events within `run`:

*   **`step`**: Triggered at `frame="0"` and `frame="3"`.
    *   `check_physics_material="1"`
    *   `max_distance="500"`
    *   `probability="1"`

### `burn` Animation

The animation for when the wizard is burning. Similar to `walk` and `run`.

*   **`frame_count`**: `6`
*   **`frame_height`**: `19`
*   **`frame_wait`**: `0.085`
*   **`frame_width`**: `16`
*   **`frames_per_row`**: `6`
*   **`pos_x`**: `0`
*   **`pos_y`**: `21`

#### Events within `burn`:

*   **`step`**: Triggered at `frame="0"` and `frame="3"`.
    *   `check_physics_material="1"`
    *   `max_distance="500"`
    *   `probability="1"`

### `attack_ranged` Animation

The animation for the wizard's ranged attack.

*   **`frame_count`**: `7`
*   **`frame_height`**: `20`
*   **`frame_wait`**: `0.08`
*   **`frame_width`**: `17`
*   **`frames_per_row`**: `6`
*   **`loop`**: `0` (Does not loop)
*   **`pos_x`**: `0`
*   **`pos_y`**: `41`
*   **`shrink_by_one_pixel`**: `1`

#### Events within `attack_ranged`:

*   **`shoot_magic`**: Triggered at `frame="5"`.
    *   `check_physics_material="0"`: Does not check physics materials.
    *   `max_distance="500"`
    *   `on_finished="0"`: Event does not trigger upon animation completion.
    *   `probability="1"`

### `fly_idle` Animation

The idle animation when the wizard is flying.

*   **`frame_count`**: `4`
*   **`frame_height`**: `21`
*   **`frame_wait`**: `0.12`
*   **`frame_width`**: `18`
*   **`frames_per_row`**: `15`
*   **`pos_x`**: `0`
*   **`pos_y`**: `81`
*   **`shrink_by_one_pixel`**: `1`

### `fly_move` Animation

The movement animation when the wizard is flying.

*   **`frame_count`**: `4`
*   **`frame_height`**: `21`
*   **`frame_wait`**: `0.12`
*   **`frame_width`**: `18`
*   **`frames_per_row`**: `15`
*   **`pos_x`**: `0`
*   **`pos_y`**: `102`
*   **`shrink_by_one_pixel`**: `1`

## Hotspots

Defines interaction points for the sprite.

### `cape` Hotspot

*   **`color`**: `ff` (Represents alpha channel, fully opaque)

This hotspot likely defines the visual area of the wizard's cape for potential interactions or visual effects.