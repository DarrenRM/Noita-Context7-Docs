---
title: Terrain Hole 02
category: entities/buildings/biome_modifiers
---

# Terrain Hole 02

This entity defines a specific type of terrain hole biome modifier in Noita. It inherits its base functionality from `terrain_hole_01.xml` and customizes its visual appearance using a unique pixel scene.

## Key Components

### Base Entity
*   **`file="data/entities/buildings/biome_modifiers/terrain_hole_01.xml"`**: This indicates that `terrain_hole_01.xml` serves as the foundational template for this entity. It inherits all properties and behaviors from its parent unless explicitly overridden.

### Pixel Scene Component
*   **`PixelSceneComponent`**: This component is responsible for defining the visual representation of the biome modifier.
    *   **`pixel_scene="data/biome_impl/biome_modifiers/hole_02.png"`**: This attribute points to the specific `.png` file that dictates the shape and appearance of this terrain hole. This is the primary differentiator from other terrain hole entities.