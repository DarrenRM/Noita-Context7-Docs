---
title: Wizard Weaken Sprite Definitions
category: entities/enemies_gfx
---

# Wizard Weaken Sprite Definitions

This document details the sprite and animation definitions for the "wizard_weaken" enemy in Noita. It outlines the visual assets and their associated animations, including frame data and specific events triggered during animations.

## Sprite Definition

The main `<Sprite>` tag defines the core visual properties and links to the sprite sheet and hotspot data.

### Key Attributes:

*   **filename**: `data/enemies_gfx/wizard_weaken.png` - Path to the sprite image file.
*   **hotspots\_filename**: `data/enemies_gfx/wizard_hotspots.png` - Path to the hotspot definition file.
*   **offset\_x**: `8` - Horizontal offset for the sprite.
*   **offset\_y**: `14` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The `<Sprite>` element contains multiple `<RectAnimation>` tags, each defining a distinct animation.

### `stand` Animation

*   **name**: `stand`
*   **frame\_count**: `6`
*   **frame\_width**: `16`
*   **frame\_height**: `19`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.1`
*   **pos\_x**: `0`
*   **pos\_y**: `1`

### `walk` Animation

*   **name**: `walk`
*   **frame\_count**: `6`
*   **frame\_width**: `16`
*   **frame\_height**: `19`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.085`
*   **pos\_x**: `0`
*   **pos\_y**: `21`
*   **Events**:
    *   `step` event triggered at frame `0` and `3`.

### `run` Animation

*   **name**: `run`
*   **frame\_count**: `6`
*   **frame\_width**: `16`
*   **frame\_height**: `19`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.085`
*   **pos\_x**: `0`
*   **pos\_y**: `21`
*   **Events**:
    *   `step` event triggered at frame `0` and `3`.

### `burn` Animation

*   **name**: `burn`
*   **frame\_count**: `6`
*   **frame\_width**: `16`
*   **frame\_height**: `19`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.085`
*   **pos\_x**: `0`
*   **pos\_y**: `21`
*   **Events**:
    *   `step` event triggered at frame `0` and `3`.

### `attack_ranged` Animation

*   **name**: `attack_ranged`
*   **frame\_count**: `7`
*   **frame\_width**: `17`
*   **frame\_height**: `20`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.08`
*   **pos\_x**: `0`
*   **pos\_y**: `41`
*   **shrink\_by\_one\_pixel**: `1`
*   **loop**: `0` (This animation does not loop)
*   **Events**:
    *   `shoot_magic` event triggered at frame `5`.

### `fly_idle` Animation

*   **name**: `fly_idle`
*   **frame\_count**: `4`
*   **frame\_width**: `17`
*   **frame\_height**: `20`
*   **frames\_per\_row**: `15`
*   **frame\_wait**: `0.12`
*   **pos\_x**: `0`
*   **pos\_y**: `81`
*   **shrink\_by\_one\_pixel**: `1`

### `fly_move` Animation

*   **name**: `fly_move`
*   **frame\_count**: `4`
*   **frame\_width**: `17`
*   **frame\_height**: `20`
*   **frames\_per\_row**: `15`
*   **frame\_wait**: `0.12`
*   **pos\_x**: `0`
*   **pos\_y**: `101`
*   **shrink\_by\_one\_pixel**: `1`

## Hotspots

### `cape` Hotspot

*   **name**: `cape`
*   **color**: `ff` (Represents alpha channel, fully opaque)

This section defines a specific visual point of interest on the sprite, likely used for collision or attachment points.