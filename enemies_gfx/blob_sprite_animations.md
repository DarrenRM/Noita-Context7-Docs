---
title: Blob Sprite Animations
category: data/enemies_gfx
---

# Blob Sprite Animations

This document details the sprite animations for the "Blob" enemy in Noita, focusing on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/blob.png` - Path to the sprite sheet.
*   **offset\_x**: `7` - Horizontal offset for the sprite.
*   **offset\_y**: `13` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation played by default.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation.

### Stand Animation

*   **name**: `"stand"`
*   **frame\_count**: `6`
*   **frame\_width**: `14`
*   **frame\_height**: `16`
*   **frame\_wait**: `0.16`
*   **frames\_per\_row**: `8`
*   **pos\_x**: `0`
*   **pos\_y**: `1`

### Walk Animation

*   **name**: `"walk"`
*   **frame\_count**: `6`
*   **frame\_width**: `15`
*   **frame\_height**: `17`
*   **frame\_wait**: `0.1`
*   **frames\_per\_row**: `8`
*   **pos\_x**: `0`
*   **pos\_y**: `18`
*   **shrink\_by\_one\_pixel**: `1`
*   **Events**:
    *   `step` event at frame `2` and `5`.

### Run Animation

*   **name**: `"run"`
*   **frame\_count**: `6`
*   **frame\_width**: `15`
*   **frame\_height**: `17`
*   **frame\_wait**: `0.1`
*   **frames\_per\_row**: `8`
*   **pos\_x**: `0`
*   **pos\_y**: `18`
*   **shrink\_by\_one\_pixel**: `1`
*   **Events**:
    *   `step` event at frame `2` and `5`.

### Burn Animation

*   **name**: `"burn"`
*   **frame\_count**: `6`
*   **frame\_width**: `15`
*   **frame\_height**: `17`
*   **frame\_wait**: `0.1`
*   **frames\_per\_row**: `8`
*   **pos\_x**: `0`
*   **pos\_y**: `18`
*   **shrink\_by\_one\_pixel**: `1`
*   **Events**:
    *   `step` event at frame `2` and `5`.

### Jump Up Animation

*   **name**: `"jump_up"`
*   **frame\_count**: `3`
*   **frame\_width**: `15`
*   **frame\_height**: `17`
*   **frame\_wait**: `0.082`
*   **frames\_per\_row**: `8`
*   **pos\_x**: `0`
*   **pos\_y**: `35`
*   **shrink\_by\_one\_pixel**: `1`
*   **loop**: `0` (Does not loop)
*   **Events**:
    *   `jump` event at frame `0`.

### Jump Fall Animation

*   **name**: `"jump_fall"`
*   **frame\_count**: `2`
*   **frame\_width**: `15`
*   **frame\_height**: `17`
*   **frame\_wait**: `0.082`
*   **frames\_per\_row**: `8`
*   **pos\_x**: `0`
*   **pos\_y**: `52`
*   **shrink\_by\_one\_pixel**: `1`
*   **loop**: `0` (Does not loop)

### Land Animation

*   **name**: `"land"`
*   **frame\_count**: `4`
*   **frame\_width**: `15`
*   **frame\_height**: `17`
*   **frame\_wait**: `0.074`
*   **frames\_per\_row**: `8`
*   **pos\_x**: `0`
*   **pos\_y**: `69`
*   **shrink\_by\_one\_pixel**: `1`
*   **loop**: `0` (Does not loop)
*   **Events**:
    *   `land` event at frame `0`.

### Attack Animation

*   **name**: `"attack"`
*   **frame\_count**: `5`
*   **frame\_width**: `21`
*   **frame\_height**: `17`
*   **frame\_wait**: `0.08`
*   **frames\_per\_row**: `8`
*   **pos\_x**: `0`
*   **pos\_y**: `86`
*   **shrink\_by\_one\_pixel**: `1`
*   **loop**: `0` (Does not loop)
*   **Events**:
    *   `bite` event at frame `3`.

## Animation Events

Events within `<RectAnimation>` tags trigger specific game actions at certain frames.

### Key Event Attributes:

*   **name**: The name of the event (e.g., `step`, `jump`, `land`, `bite`).
*   **frame**: The frame number at which the event occurs.
*   **probability**: The chance of the event triggering (usually `1` for guaranteed events).
*   **check\_physics\_material**: If `1`, the event might be influenced by the physics material of the ground.
*   **max\_distance**: Maximum distance for certain event checks.
*   **on\_finished**: Controls behavior after the event (e.g., `0` means continue animation).