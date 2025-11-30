---
title: Wizard Returner Sprite Definitions
category: enemies_gfx
---

# Wizard Returner Sprite Definitions

This document details the sprite and animation definitions for the "Wizard Returner" enemy in Noita, as found in `wizard_returner.xml`. This file is crucial for understanding how the enemy visually appears and animates in-game.

## Core Sprite Attributes

These attributes define the base sprite image and its positioning.

*   **`filename`**: `data/enemies_gfx/wizard_returner.png` - The primary image file for the wizard.
*   **`hotspots_filename`**: `data/enemies_gfx/wizard_hotspots.png` - An associated file defining specific points (hotspots) on the sprite, often used for hit detection or attachment points.
*   **`offset_x`**: `8` - Horizontal offset applied to the sprite's origin.
*   **`offset_y`**: `14` - Vertical offset applied to the sprite's origin.
*   **`default_animation`**: `"stand"` - The animation that plays by default when the entity is idle.

## Animations

The following table summarizes the key animations defined for the Wizard Returner. Each animation is a sequence of frames from the sprite sheet.

| Animation Name   | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Pos X | Pos Y | Loop | Shrink By One Pixel | Notes