---
title: Terrain Hole 01 Entity
category: entities/biome_modifiers
---

# Terrain Hole 01 Entity

This entity defines a simple terrain hole effect.

## Key Components

### PixelSceneComponent
This component defines the visual representation of the terrain hole.

*   **pixel_scene**: `data/biome_impl/biome_modifiers/hole_01.png` - Specifies the image file used for the hole's appearance.

### LifetimeComponent
This component controls how long the terrain hole persists.

*   **lifetime**: `2` - The duration in seconds for which the hole will exist before disappearing.