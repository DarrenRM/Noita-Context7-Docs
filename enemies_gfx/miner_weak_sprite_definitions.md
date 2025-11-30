---
title: Miner (Weak) Sprite Definitions
category: data/enemies_gfx
---

# Miner (Weak) Sprite Definitions

This document details the sprite and animation definitions for the "miner_weak" enemy in Noita, as found in `data/enemies_gfx/miner_weak.xml`. This file defines the visual appearance and animation sequences for this enemy.

## Sprite Definition

The main `<Sprite>` tag defines the core visual properties and links to the sprite sheet and hotspot data.

### Key Attributes:

*   **filename**: `data/enemies_gfx/miner_weak.png` - Path to the sprite sheet image.
*   **hotspots\_filename**: `data/enemies_gfx/miner_hotspots.png` - Path to the image defining collision/interaction points.
*   **offset\_x**: `7` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `12` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

### Hotspots:

*   **hand**: Defined with a red color (`ff0000`), likely indicating a point of interaction or attack.

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation sequence.

### Key Animation Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "attack", "walk").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **pos\_x**: The horizontal starting position of the animation frames on the sprite sheet.
*   **pos\_y**: The vertical starting position of the animation frames on the sprite sheet.
*   **loop**: `0` indicates the animation plays only once; omitted or `1` implies looping.
*   **shrink\_by\_one\_pixel**: `1` indicates a slight scaling adjustment.

### Notable Animations and Events:

| Animation Name   | Frame Count | Frame Wait | Loop | Key Events