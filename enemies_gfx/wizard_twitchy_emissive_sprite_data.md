---
title: Wizard Twitchy Emissive Sprite Data
category: data/enemies_gfx
---

# Wizard Twitchy Emissive Sprite Data

This document details the sprite and animation data for the "wizard_twitchy_emissive" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation for the enemy.

### Key Attributes:

*   **filename**: `data/enemies_gfx/wizard_twitchy_emissive.png` - The path to the sprite sheet.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `14` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The `<RectAnimation>` tags define individual animations, including their frame data and events.

### Common Attributes for `RectAnimation`:

*   **name**: The name of the animation (e.g., "stand", "walk", "attack\_ranged").
*   **frame\_count**: Total number of frames in the animation.
*   **frame\_width**: Width of each individual frame.
*   **frame\_height**: Height of each individual frame.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: X-coordinate of the top-left corner of the animation's frame area on the sprite sheet.
*   **pos\_y**: Y-coordinate of the top-left corner of the animation's frame area on the sprite sheet.
*   **loop**: `0` indicates the animation does not loop (e.g., for attack animations). Defaults to looping.
*   **shrink\_by\_one\_pixel**: `1` indicates frames are slightly smaller than the defined `frame_width`/`frame_height`.

### Notable Animations:

#### `stand`

*   **frame\_count**: `6`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.05`
*   **frame\_width**: `16`
*   **frames\_per\_row**: `6`
*   **pos\_y**: `1`

#### `walk`

*   **frame\_count**: `6`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.045`
*   **frame\_width**: `16`
*   **frames\_per\_row**: `6`
*   **pos\_y**: `21`
*   **Events**:
    *   `step` event triggered on frame `0` and `3`.

#### `run`

*   **frame\_count**: `6`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.045`
*   **frame\_width**: `16`
*   **frames\_per\_row**: `6`
*   **pos\_y**: `21`
*   **Events**:
    *   `step` event triggered on frame `0` and `3`.

#### `burn`

*   **frame\_count**: `6`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.045`
*   **frame\_width**: `16`
*   **frames\_per\_row**: `6`
*   **pos\_y**: `21`
*   **Events**:
    *   `step` event triggered on frame `0` and `3`.

#### `attack_ranged`

*   **frame\_count**: `7`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.04`
*   **frame\_width**: `17`
*   **frames\_per\_row**: `6`
*   **loop**: `0` (Does not loop)
*   **pos\_y**: `41`
*   **shrink\_by\_one\_pixel**: `1`
*   **Events**:
    *   `shoot_magic` event triggered on frame `5`.

#### `fly_idle`

*   **frame\_count**: `4`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.06`
*   **frame\_width**: `17`
*   **frames\_per\_row**: `15`
*   **pos\_y**: `81`
*   **shrink\_by\_one\_pixel**: `1`

#### `fly_move`

*   **frame\_count**: `4`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.06`
*   **frame\_width**: `17`
*   **frames\_per\_row**: `15`
*   **pos\_y**: `101`
*   **shrink\_by\_one\_pixel**: `1`

## Events

Events are triggered at specific frames within an animation and can initiate game actions.

### Common Attributes for `Event`:

*   **name**: The name of the event (e.g., "step", "shoot\_magic").
*   **frame**: The frame number on which the event is triggered.
*   **check\_physics\_material**: `1` indicates the game should check the physics material of the ground/surface.
*   **max\_distance**: Maximum distance for certain event checks.
*   **on\_finished**: `0` typically means the event does not stop the animation.
*   **probability**: `1` means the event is guaranteed to trigger if conditions are met.

## Hotspots

Hotspots define specific points or areas on the sprite, often used for collision or visual effects.

### `cape`

*   **color**: `"ff"` (likely represents a specific color channel or identifier for the hotspot).
*   **name**: `"cape"` - Identifies this hotspot as the character's cape.