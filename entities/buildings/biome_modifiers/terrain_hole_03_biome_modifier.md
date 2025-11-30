---
title: Terrain Hole 03 Biome Modifier
category: entities/buildings/biome_modifiers
---

# Terrain Hole 03 Biome Modifier

This entity defines a biome modifier that creates a specific terrain hole pattern. It inherits its base functionality from `terrain_hole_01.xml` and customizes its visual appearance using a pixel scene.

## Key Components

### Base Entity

*   **`Base file="data/entities/buildings/biome_modifiers/terrain_hole_01.xml"`**: Inherits core properties and behaviors from a generic terrain hole entity. This likely includes placement logic and interaction with the biome system.

### Pixel Scene Component

*   **`PixelSceneComponent`**: This component is responsible for defining the visual shape and texture of the terrain hole.
    *   **`pixel_scene="data/biome_impl/biome_modifiers/hole_03.png"`**: Specifies the image file that dictates the terrain hole's appearance. This PNG likely contains alpha channels or color information to define the hole's boundaries and any associated visual effects.