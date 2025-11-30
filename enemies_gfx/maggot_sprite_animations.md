---
title: Maggot Sprite Animations
category: data/enemies_gfx
---

# Maggot Sprite Animations

This document details the sprite animations for the Maggot enemy in Noita, as defined in `maggot.xml`. It focuses on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/maggot.png` - The path to the sprite sheet.
*   **offset\_x**: `14` - Horizontal offset for the sprite.
*   **offset\_y**: `20` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The Maggot has several distinct animations, each defined by a `<RectAnimation>` tag.

### `stand` Animation

*   **name**: `"stand"`
*   **frame\_count**: `7`
*   **frame\_width**: `28`
*   **frame\_height**: `24`
*   **frames\_per\_row**: `8`
*   **frame\_wait**: `0.1`
*   **pos\_x**: `0`
*   **pos\_y**: `1`

### `walk` Animation

*   **name**: `"walk"`
*   **frame\_count**: `6`
*   **frame\_width**: `29`
*   **frame\_height**: `25`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.085`
*   **pos\_x**: `0`
*   **pos\_y**: `26`
*   **shrink\_by\_one\_pixel**: `1`

#### Events:

*   **step**: Triggered at frame `0` and `3`. `check_physics_material="1"` suggests it's related to ground interaction.

### `run` Animation

*   **name**: `"run"`
*   **frame\_count**: `6`
*   **frame\_width**: `29`
*   **frame\_height**: `25`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.085`
*   **pos\_x**: `0`
*   **pos\_y**: `26`
*   **shrink\_by\_one\_pixel**: `1`

#### Events:

*   **step**: Triggered at frame `0` and `3`. `check_physics_material="1"` suggests it's related to ground interaction.

### `burn` Animation

*   **name**: `"burn"`
*   **frame\_count**: `6`
*   **frame\_width**: `29`
*   **frame\_height**: `25`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.085`
*   **pos\_x**: `0`
*   **pos\_y**: `26`
*   **shrink\_by\_one\_pixel**: `1`

#### Events:

*   **step**: Triggered at frame `0` and `3`. `check_physics_material="1"` suggests it's related to ground interaction.

### `attack_ranged` Animation

*   **name**: `"attack_ranged"`
*   **frame\_count**: `8`
*   **frame\_width**: `29`
*   **frame\_height**: `25`
*   **frames\_per\_row**: `8`
*   **frame\_wait**: `0.15`
*   **pos\_x**: `0`
*   **pos\_y**: `51`
*   **shrink\_by\_one\_pixel**: `1`
*   **loop**: `0` (This animation does not loop)

#### Events:

*   **spit\_slime**: Triggered at frame `5`. `check_physics_material="0"` indicates this event is not tied to physics material.

### `attack` Animation

*   **name**: `"attack"`
*   **frame\_count**: `8`
*   **frame\_width**: `29`
*   **frame\_height**: `25`
*   **frames\_per\_row**: `8`
*   **frame\_wait**: `0.08`
*   **pos\_x**: `0`
*   **pos\_y**: `51`
*   **shrink\_by\_one\_pixel**: `1`
*   **loop**: `0` (This animation does not loop)

#### Events:

*   **bite**: Triggered at frame `5`. `check_physics_material="0"` indicates this event is not tied to physics material.