---
title: Dark Wizard Sprite Definitions
category: entities
---

# Dark Wizard Sprite Definitions

This document details the sprite and animation definitions for the Dark Wizard enemy in Noita. It outlines the graphical assets used and the various animations available, including their frame data and specific events.

## Sprite Attributes

The main `<Sprite>` tag defines the core graphical properties of the Dark Wizard.

*   **filename**: `data/enemies_gfx/wizard_dark.png` - The primary image file for the sprite.
*   **hotspots\_filename**: `data/enemies_gfx/wizard_hotspots.png` - The image file defining collision and interaction points.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `14` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default when the entity is idle.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` elements, each defining a distinct animation.

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
    *   `step` at frame `0` (probability `1`)
    *   `step` at frame `3` (probability `1`)

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
    *   `step` at frame `0` (probability `1`)
    *   `step` at frame `3` (probability `1`)

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
    *   `step` at frame `0` (probability `1`)
    *   `step` at frame `3` (probability `1`)

### `attack_ranged` Animation

*   **name**: `attack_ranged`
*   **frame\_count**: `7`
*   **frame\_width**: `17`
*   **frame\_height**: `20`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.08`
*   **pos\_x**: `0`
*   **pos\_y**: `41`
*   **loop**: `0` (This animation does not loop)
*   **shrink\_by\_one\_pixel**: `1`
*   **Events**:
    *   `shoot_magic` at frame `5` (probability `1`)

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

*   **name**: `cape`
*   **color**: `ff` (Represents alpha channel, fully opaque)

This section defines a specific interaction or visual point named "cape".