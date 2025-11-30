---
title: Terrain Water Ball Entity
category: entities
---

# Terrain Water Ball Entity

This entity defines a visual and functional element that modifies terrain, specifically creating a "water ball" effect.

## Key Components

### PixelSceneComponent
This component handles the visual representation of the entity.

*   **pixel\_scene**: `data/biome_impl/biome_modifiers/water_ball.png` - Specifies the image file used for the visual effect.
*   **offset\_x**: `16` - The horizontal offset of the visual element.
*   **offset\_y**: `16` - The vertical offset of the visual element.

### LifetimeComponent
This component determines how long the entity persists.

*   **lifetime**: `2` - The duration in seconds the entity will exist before disappearing.