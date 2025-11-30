---
title: Swamp Ball Biome Modifier
category: entities
---

---

# Swamp Ball Biome Modifier

This entity defines a biome modifier that creates a "swamp ball" effect.

## Key Components

### PixelSceneComponent
This component defines the visual representation of the biome modifier.

*   **pixel_scene**: `data/biome_impl/biome_modifiers/swamp_ball.png` - The image file used for the modifier's visual.
*   **offset\_x**: `16` - Horizontal offset for the visual.
*   **offset\_y**: `16` - Vertical offset for the visual.

### LifetimeComponent
This component determines how long the biome modifier persists.

*   **lifetime**: `2` - The duration in seconds the modifier will be active.