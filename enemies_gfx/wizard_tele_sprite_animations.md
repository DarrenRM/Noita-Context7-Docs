---
title: Wizard Tele Sprite Animations
category: data/enemies_gfx
---

# Wizard Tele Sprite Animations

This document details the sprite animations for the "wizard_tele" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main sprite definition for the wizard_tele.

### Key Attributes:

*   **filename**: `data/enemies_gfx/wizard_tele.png` - The primary image file for the sprite.
*   **hotspots_filename**: `data/enemies_gfx/wizard_hotspots.png` - File containing collision/hitbox data.
*   **offset_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset_y**: `14` - Vertical offset for the sprite's origin.
*   **default_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### `stand` Animation

*   **name**: `"stand"`
*   **frame\_count**: `6`
*   **frame\_width**: `16`
*   **frame\_height**: `19`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.1`
*   **pos\_x**: `0`
*   **pos\_y**: `1`

### `walk` Animation

*   **name**: `"walk"`
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

*   **name**: `"run"`
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

*   **name**: `"burn"`
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

*   **name**: `"attack_ranged"`
*   **frame\_count**: `7`
*   **frame\_width**: `17`
*   **frame\_height**: `20`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.08`
*   **pos\_x**: `0`
*   **pos\_y**: `41`
*   **loop**: `0` (Does not loop)
*   **shrink\_by\_one\_pixel**: `1`
*   **Events**:
    *   `voc_attack` at frame `0` (probability `1`)

### `fly_idle` Animation

*   **name**: `"fly_idle"`
*   **frame\_count**: `4`
*   **frame\_width**: `17`
*   **frame\_height**: `20`
*   **frames\_per\_row**: `15`
*   **frame\_wait**: `0.12`
*   **pos\_x**: `0`
*   **pos\_y**: `81`
*   **shrink\_by\_one\_pixel**: `1`

### `fly_move` Animation

*   **name**: `"fly_move"`
*   **frame\_count**: `4`
*   **frame\_width**: `17`
*   **frame\_height**: `20`
*   **frames\_per\_row**: `15`
*   **frame\_wait**: `0.12`
*   **pos\_x**: `0`
*   **pos\_y**: `101`
*   **shrink\_by\_one\_pixel**: `1`

## Hotspots

Defines specific points or areas within the sprite.

### `cape` Hotspot

*   **name**: `"cape"`
*   **color**: `"ff"` (Likely indicates a specific color channel or type)