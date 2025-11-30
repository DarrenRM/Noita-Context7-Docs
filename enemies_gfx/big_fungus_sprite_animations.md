---
title: Big Fungus Sprite Animations
category: data/enemies_gfx
---

# Big Fungus Sprite Animations

This document details the sprite animations for the "Big Fungus" enemy in Noita, as defined in its XML configuration file. It focuses on the key attributes of the sprite and its various animations.

## Sprite Attributes

The main `<Sprite>` tag defines the base image and its default animation.

*   **filename**: `data/enemies_gfx/fungus_big.png` - The path to the sprite sheet image.
*   **offset\_x**: `17` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `30` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the enemy is idle.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation.

### Stand Animation

*   **name**: `"stand"`
*   **frame\_count**: `8`
*   **frame\_width**: `34`
*   **frame\_height**: `34`
*   **frames\_per\_row**: `8`
*   **frame\_wait**: `0.18` seconds per frame.
*   **pos\_x**: `0`
*   **pos\_y**: `0` - This animation uses the top row of the sprite sheet.

### Walk Animation

*   **name**: `"walk"`
*   **frame\_count**: `6`
*   **frame\_width**: `34`
*   **frame\_height**: `34`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.16` seconds per frame.
*   **pos\_x**: `0`
*   **pos\_y**: `34` - This animation uses the second row of the sprite sheet.
*   **Events**:
    *   `step` event triggered at frame `0` and `3`.

### Run Animation

*   **name**: `"run"`
*   **frame\_count**: `6`
*   **frame\_width**: `34`
*   **frame\_height**: `34`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.14` seconds per frame.
*   **pos\_x**: `0`
*   **pos\_y**: `34` - This animation also uses the second row of the sprite sheet, similar to "walk".
*   **Events**:
    *   `step` event triggered at frame `0` and `3`.

### Burn Animation

*   **name**: `"burn"`
*   **frame\_count**: `6`
*   **frame\_width**: `34`
*   **frame\_height**: `34`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.14` seconds per frame.
*   **pos\_x**: `0`
*   **pos\_y**: `34` - This animation also uses the second row of the sprite sheet.
*   **Events**:
    *   `step` event triggered at frame `0` and `3`.

### Jump Up Animation

*   **name**: `"jump_up"`
*   **frame\_count**: `1`
*   **frame\_width**: `34`
*   **frame\_height**: `34`
*   **frames\_per\_row**: `8`
*   **frame\_wait**: `0.2` seconds per frame.
*   **pos\_x**: `102`
*   **pos\_y**: `34` - This animation uses a specific frame from the sprite sheet.
*   **Events**:
    *   `jump` event triggered at frame `0`.

### Jump Fall Animation

*   **name**: `"jump_fall"`
*   **frame\_count**: `1`
*   **frame\_width**: `34`
*   **frame\_height**: `34`
*   **frames\_per\_row**: `8`
*   **frame\_wait**: `0.2` seconds per frame.
*   **pos\_x**: `102`
*   **pos\_y**: `34` - This animation uses the same frame as `jump_up`.

## Event Details

Events within animations can trigger specific game actions.

### `step` Event

*   **check\_physics\_material**: `1` - Indicates that physics material should be checked.
*   **max\_distance**: `500` - The maximum distance for the check.
*   **on\_finished**: `0` - No specific action on animation finish.
*   **probability**: `1` - The event always triggers if conditions are met.

### `jump` Event

*   **check\_physics\_material**: `1` - Indicates that physics material should be checked.
*   **max\_distance**: `500` - The maximum distance for the check.
*   **on\_finished**: `0` - No specific action on animation finish.
*   **probability**: `1` - The event always triggers if conditions are met.