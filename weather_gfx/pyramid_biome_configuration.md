---
title: Pyramid Biome Configuration
category: guides
---

{
  "title": "Pyramid Biome Configuration",
  "category": "biome"
}
```

# Pyramid Biome Configuration

This document details the configuration for the Pyramid biome in Noita, focusing on its visual, structural, and material properties.

## Topology

The `Topology` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes:

*   **`name`**: `$biome_pyramid` - Internal identifier for this biome.
*   **`type`**: `BIOME_WANG_TILE` - Indicates this biome uses Wang Tiles for generation.
*   **`background_image`**: `data/weather_gfx/background_pyramid.png` - The main background image for the biome.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: Paths to specific edge graphics for the background.
*   **`background_edge_priority`**: `9` - Determines the rendering order of background edges.
*   **`wang_template_file`**: `data/wang_tiles/pyramid.png` - The image file containing the Wang Tile patterns for this biome.
*   **`lua_script`**: `data/scripts/biomes/pyramid.lua` - The associated Lua script that governs biome-specific behaviors.
*   **`wang_map_width`, `wang_map_height`**: `256`, `256` - Dimensions of the Wang Tile map.
*   **`audio_ambience`**: `wandcave` - The primary ambient soundscape for the biome.
*   **`audio_ambience_surface`**: `desert` - Ambient soundscape for the surface layer.
*   **`has_rain`**: `0` - Disables rain in this biome.

### BitmapCaves Configuration:

This section defines parameters for generating cave structures within the biome.

*   **`size_x`, `size_y`**: `516`, `256` - Dimensions of the bitmap used for cave generation.
*   **`spawn_percent`**: `0` - Controls the probability of cave spawning.
*   **`blob_caves_count_min`, `blob_caves_count_max`**: `0`, `1` - Range for the number of blob-like cave formations.
*   **`blob_caves_radius_min`, `blob_caves_radius_max`**: `1`, `1` - Range for the radius of blob caves.
*   **`blob_caves_strength_min`, `blob_caves_strength_max`**: `1.2`, `2` - Controls the intensity/density of blob caves.
*   **`cave_childs_min`, `cave_childs_max`**: `0`, `1` - Range for the number of child caves.
*   **`cave_count_min`, `cave_count_max`**: `1`, `2` - Range for the total number of caves.
*   **`cave_strength_min`, `cave_strength_max`**: `0.2`, `1.8` - Controls the intensity/density of general caves.
*   **`mountain_count_min`, `mountain_count_max`**: `0`, `0` - No mountains are generated.

## Materials

The `Materials` element defines the different types of materials that can be found within the biome and their properties.

### Material Components:

Each `MaterialComponent` defines a specific material and how it's distributed.

| Attribute                 | Description