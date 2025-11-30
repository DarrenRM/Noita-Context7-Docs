---
title: Failed Alchemist Sprite Animations
category: data/enemies_gfx/
---

# Failed Alchemist Sprite Animations

This document details the sprite animations for the Failed Alchemist enemy in Noita, as defined in its `failed_alchemist.xml` file. It focuses on key attributes of the sprite and its various animations.

## Sprite Attributes

The main `<Sprite>` tag defines the base properties for the enemy's visual representation.

*   **`filename`**: `data/enemies_gfx/failed_alchemist.png` - The path to the sprite sheet image.
*   **`default_animation`**: `"stand"` - The animation that plays by default when the enemy is idle.
*   **`offset_x`**: `21` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `30` - Vertical offset for the sprite's origin.

## Animations

The Failed Alchemist has several distinct animations, each defined by a `<RectAnimation>` tag.

### Stand Animation

*   **`name`**: `"stand"`
*   **`frame_count`**: `6`
*   **`frame_width`**: `42`
*   **`frame_height`**: `34`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.14` seconds per frame.
*   **`pos_x`**: `0`
*   **`pos_y`**: `1` - Defines the starting position of this animation strip on the sprite sheet.

### Walk Animation

*   **`name`**: `"walk"`
*   **`frame_count`**: `8`
*   **`frame_width`**: `43`
*   **`frame_height`**: `35`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.12` seconds per frame.
*   **`pos_x`**: `0`
*   **`pos_y`**: `36`
*   **`shrink_by_one_pixel`**: `1` - Indicates a slight shrinking effect for this animation.
*   **Events**:
    *   `step` event triggered at frame `3` and `7`.

### Run Animation

*   **`name`**: `"run"`
*   **`frame_count`**: `8`
*   **`frame_width`**: `43`
*   **`frame_height`**: `35`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.1` seconds per frame.
*   **`pos_x`**: `0`
*   **`pos_y`**: `36`
*   **`shrink_by_one_pixel`**: `1`
*   **Events**:
    *   `step` event triggered at frame `3` and `7`.

### Burn Animation

*   **`name`**: `"burn"`
*   **`frame_count`**: `8`
*   **`frame_width`**: `43`
*   **`frame_height`**: `35`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.09` seconds per frame.
*   **`pos_x`**: `0`
*   **`pos_y`**: `36`
*   **`shrink_by_one_pixel`**: `1`
*   **Events**:
    *   `step` event triggered at frame `3` and `7`.

### Attack Animation

*   **`name`**: `"attack"`
*   **`frame_count`**: `12`
*   **`frame_width`**: `42`
*   **`frame_height`**: `34`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.09` seconds per frame.
*   **`loop`**: `0` (This animation does not loop).
*   **`pos_x`**: `0`
*   **`pos_y`**: `71`
*   **Events**:
    *   `attack_melee` event triggered at frame `6`.
    *   `voc_attack` event triggered at frame `6`.

### Attack Finish Animation

*   **`name`**: `"attack_finish"`
*   **`frame_count`**: `12`
*   **`frame_width`**: `42`
*   **`frame_height`**: `34`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.07` seconds per frame.
*   **`loop`**: `0`
*   **`pos_x`**: `0`
*   **`pos_y`**: `71`
*   **Events**:
    *   `attack_melee` event triggered at frame `6`.
    *   `voc_attack` event triggered at frame `6`.

### Jump Prepare Animation

*   **`name`**: `"jump_prepare"`
*   **`frame_count`**: `3`
*   **`frame_width`**: `42`
*   **`frame_height`**: `34`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.07` seconds per frame.
*   **`loop`**: `0`
*   **`pos_x`**: `0`
*   **`pos_y`**: `106`

### Jump Up Animation

*   **`name`**: `"jump_up"`
*   **`frame_count`**: `2`
*   **`frame_width`**: `42`
*   **`frame_height`**: `34`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.07` seconds per frame.
*   **`loop`**: `0`
*   **`pos_x`**: `0`
*   **`pos_y`**: `141`
*   **Events**:
    *   `jump` event triggered at frame `0`.

### Jump Fall Animation

*   **`name`**: `"jump_fall"`
*   **`frame_count`**: `4`
*   **`frame_width`**: `42`
*   **`frame_height`**: `34`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.09` seconds per frame.
*   **`loop`**: `0`
*   **`pos_x`**: `0`
*   **`pos_y`**: `176`

### Land Animation

*   **`name`**: `"land"`
*   **`frame_count`**: `4`
*   **`frame_width`**: `42`
*   **`frame_height`**: `34`
*   **`frames_per_row`**: `12`
*   **`frame_wait`**: `0.09` seconds per frame.
*   **`loop`**: `0`
*   **`pos_x`**: `0`
*   **`pos_y`**: `211`