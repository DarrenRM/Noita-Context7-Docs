---
title: Wizard Swapper Sprite Data
category: entities/gfx
---

# Wizard Swapper Sprite Data

This document details the sprite and animation data for the "Wizard Swapper" enemy in Noita, as defined in `wizard_swapper.xml`.

## Sprite Definition

The main `<Sprite>` element defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/enemies_gfx/wizard_swapper.png` - Path to the sprite sheet.
*   **hotspots_filename**: `data/enemies_gfx/wizard_hotspots.png` - Path to the sprite sheet containing hotspot data.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `14` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The `<Sprite>` element contains multiple `<RectAnimation>` elements, each defining a specific animation.

### `stand` Animation

*   **frame\_count**: `6`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.1`
*   **frame\_width**: `16`
*   **frames\_per\_row**: `6`
*   **name**: `"stand"`
*   **pos\_x**: `0`
*   **pos\_y**: `1`

### `walk` Animation

*   **frame\_count**: `6`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.085`
*   **frame\_width**: `16`
*   **frames\_per\_row**: `6`
*   **name**: `"walk"`
*   **pos\_x**: `0`
*   **pos\_y**: `21`

#### Events:

*   **frame `0`**: Triggers a `"step"` event.
*   **frame `3`**: Triggers a `"step"` event.

### `run` Animation

*   **frame\_count**: `6`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.085`
*   **frame\_width**: `16`
*   **frames\_per\_row**: `6`
*   **name**: `"run"`
*   **pos\_x**: `0`
*   **pos\_y**: `21`

#### Events:

*   **frame `0`**: Triggers a `"step"` event.
*   **frame `3`**: Triggers a `"step"` event.

### `burn` Animation

*   **frame\_count**: `6`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.085`
*   **frame\_width**: `16`
*   **frames\_per\_row**: `6`
*   **name**: `"burn"`
*   **pos\_x**: `0`
*   **pos\_y**: `21`

#### Events:

*   **frame `0`**: Triggers a `"step"` event.
*   **frame `3`**: Triggers a `"step"` event.

### `attack_ranged` Animation

*   **frame\_count**: `7`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.08`
*   **frame\_width**: `17`
*   **frames\_per\_row**: `6`
*   **loop**: `0` (Does not loop)
*   **name**: `"attack_ranged"`
*   **pos\_x**: `0`
*   **pos\_y**: `41`
*   **shrink\_by\_one\_pixel**: `1`

#### Events:

*   **frame `5`**: Triggers a `"shoot_magic"` event.

### `fly_idle` Animation

*   **frame\_count**: `4`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.12`
*   **frame\_width**: `17`
*   **frames\_per\_row**: `15`
*   **name**: `"fly_idle"`
*   **pos\_x**: `0`
*   **pos\_y**: `81`
*   **shrink\_by\_one\_pixel**: `1`

### `fly_move` Animation

*   **frame\_count**: `4`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.12`
*   **frame\_width**: `17`
*   **frames\_per\_row**: `15`
*   **name**: `"fly_move"`
*   **pos\_x**: `0`
*   **pos\_y**: `101`
*   **shrink\_by\_one\_pixel**: `1`

## Hotspots

The `<Sprite>` element can also define hotspots for interaction or collision.

### `cape` Hotspot

*   **color**: `ff` (Represents alpha channel, fully opaque)
*   **name**: `"cape"`