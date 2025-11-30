---
title: Grass Ball Biome Modifier
category: entities/biome_modifiers
---

# Grass Ball Biome Modifier

This entity defines a biome modifier that introduces a "grass ball" effect.

## Key Components

### PixelSceneComponent
This component defines the visual representation of the biome modifier.

*   **pixel_scene**: `data/biome_impl/biome_modifiers/grass_ball.png` - Specifies the image file used for the visual effect.
*   **offset\_x**: `16` - The horizontal offset of the visual element.
*   **offset\_y**: `16` - The vertical offset of the visual element.

### LifetimeComponent
This component controls how long the biome modifier persists.

*   **lifetime**: `2` - The duration in seconds for which the grass ball effect will be active.