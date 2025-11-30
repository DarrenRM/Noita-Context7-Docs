---
title: Miner Santa Sprite Definitions
category: enemies_gfx
---

# Miner Santa Sprite Definitions

This document details the sprite and animation definitions for the "miner_santa" enemy in Noita. It outlines the primary sprite sheet, hotspot definitions, and various animations used by the character.

## Sprite Sheet and Hotspots

The core sprite information defines the image file and its general properties.

*   **Filename**: `data/enemies_gfx/miner_santa.png` - The main image file containing all animation frames.
*   **Hotspots Filename**: `data/enemies_gfx/miner_fire_hotspots.png` - An associated file defining specific points of interest on the sprite.
*   **Offset X**: `7` - Horizontal offset for the sprite's origin.
*   **Offset Y**: `12` - Vertical offset for the sprite's origin.
*   **Default Animation**: `stand` - The animation to play by default.

### Hotspots

*   **`hand`**: Defined with a red color (`ff0000`), likely indicating a point for weapon/item interaction or visual reference.

## Animations

The `Sprite` element contains multiple `RectAnimation` definitions, each describing a specific animation sequence.

### `stand` Animation

*   **Name**: `stand`
*   **Frame Count**: `6`
*   **Frame Size**: `18x16` pixels
*   **Frame Wait**: `0.2` seconds per frame
*   **Frames Per Row**: `6`
*   **Position**: `(0, 1)` in the sprite sheet.
*   **Shrink By One Pixel**: `1` (Applies a slight shrink effect)

### `attack` Animation

*   **Name**: `attack`
*   **Frame Count**: `7`
*   **Frame Size**: `18x16` pixels
*   **Frame Wait**: `0.05` seconds per frame
*   **Frames Per Row**: `8`
*   **Loop**: `0` (Plays once)
*   **Position**: `(0, 17)` in the sprite sheet.
*   **Shrink By One Pixel**: `1`
*   **Events**:
    *   **`hit`**: Triggered at frame `4`.

### `attack_ranged` Animation

*   **Name**: `attack_ranged`
*   **Frame Count**: `7`
*   **Frame Size**: `18x16` pixels
*   **Frame Wait**: `0.05` seconds per frame
*   **Frames Per Row**: `8`
*   **Loop**: `0` (Plays once)
*   **Position**: `(0, 17)` in the sprite sheet.
*   **Shrink By One Pixel**: `1`
*   **Events**:
    *   **`throw`**: Triggered at frame `4`.

### `walk` Animation

*   **Name**: `walk`
*   **Frame Count**: `6`
*   **Frame Size**: `18x16` pixels
*   **Frame Wait**: `0.15` seconds per frame
*   **Frames Per Row**: `6`
*   **Position**: `(0, 33)` in the sprite sheet.
*   **Shrink By One Pixel**: `1`
*   **Events**:
    *   **`step`**: Triggered at frame `2`.
    *   **`step`**: Triggered at frame `5`.

### `run` Animation

*   **Name**: `run`
*   **Frame Count**: `6`
*   **Frame Size**: `18x16` pixels
*   **Frame Wait**: `0.15` seconds per frame
*   **Frames Per Row**: `8`
*   **Position**: `(0, 33)` in the sprite sheet.
*   **Shrink By One Pixel**: `1`
*   **Events**:
    *   **`step`**: Triggered at frame `2`.
    *   **`step`**: Triggered at frame `5`.

### `burn` Animation

*   **Name**: `burn`
*   **Frame Count**: `6`
*   **Frame Size**: `18x16` pixels
*   **Frame Wait**: `0.15` seconds per frame
*   **Frames Per Row**: `8`
*   **Position**: `(0, 33)` in the sprite sheet.
*   **Shrink By One Pixel**: `1`
*   **Events**:
    *   **`step`**: Triggered at frame `2`.
    *   **`step`**: Triggered at frame `5`.

### `jump_up` Animation

*   **Name**: `jump_up`
*   **Frame Count**: `1`
*   **Frame Size**: `18x16` pixels
*   **Frame Wait**: `0.12` seconds per frame
*   **Frames Per Row**: `8`
*   **Position**: `(0, 49)` in the sprite sheet.
*   **Shrink By One Pixel**: `1`
*   **Events**:
    *   **`jump`**: Triggered at frame `0`.

### `jump_fall` Animation

*   **Name**: `jump_fall`
*   **Frame Count**: `1`
*   **Frame Size**: `18x16` pixels
*   **Frame Wait**: `0.12` seconds per frame
*   **Frames Per Row**: `8`
*   **Position**: `(0, 49)` in the sprite sheet.
*   **Shrink By One Pixel**: `1`

### `knockback` Animation

*   **Name**: `knockback`
*   **Frame Count**: `1`
*   **Frame Size**: `18x16` pixels
*   **Frame Wait**: `0.055` seconds per frame
*   **Frames Per Row**: `8`
*   **Position**: `(0, 65)` in the sprite sheet.
*   **Shrink By One Pixel**: `1`

### `lower_head` Animation

*   **Name**: `lower_head`
*   **Frame Count**: `1`
*   **Frame Size**: `18x16` pixels
*   **Frame Wait**: `0.01` seconds per frame
*   **Frames Per Row**: `8`
*   **Loop**: `0` (Plays once)
*   **Position**: `(0, 81)` in the sprite sheet.
*   **Shrink By One Pixel**: `1`

### `eat` Animation

*   **Name**: `eat`
*   **Frame Count**: `6`
*   **Frame Size**: `18x16` pixels
*   **Frame Wait**: `0.068` seconds per frame
*   **Frames Per Row**: `8`
*   **Loop**: `0` (Plays once)
*   **Position**: `(0, 81)` in the sprite sheet.
*   **Shrink By One Pixel**: `1`
*   **Events**:
    *   **`stomp`**: Triggered at frame `4`.

### `raise_head` Animation

*   **Name**: `raise_head`
*   **Frame Count**: `1`
*   **Frame Size**: `18x16` pixels
*   **Frame Wait**: `0.01` seconds per frame
*   **Frames Per Row**: `8`
*   **Loop**: `0` (Plays once)
*   **Position**: `(0, 81)` in the sprite sheet.
*   **Shrink By One Pixel**: `1`

### `alert` Animation

*   **Name**: `alert`
*   **Frame Count**: `2`
*   **Frame Size**: `18x16` pixels
*   **Frame Wait**: `0.09` seconds per frame
*   **Frames Per Row**: `8`
*   **Loop**: `0` (Plays once)
*   **Position**: `(0, 97)` in the sprite sheet.
*   **Shrink By One Pixel**: `1`