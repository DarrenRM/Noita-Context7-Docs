---
title: Funroom Biome Configuration
category: biome
---

---

# Funroom Biome Configuration

This document details the configuration for the "Funroom" biome in Noita, focusing on its generation, visual elements, and material composition.

## Topology

The `Topology` element defines the fundamental structure and generation parameters of the biome.

### Key Attributes:

*   **`name`**: "???" - The internal name for this biome topology.
*   **`type`**: "BIOME_WANG_TILE" - Indicates this biome uses Wang Tiles for generation.
*   **`background_use_neighbor`**: "0" - Disables background image blending with neighbors.
*   **`background_image`**: "data/weather_gfx/background_crypt.png" - The primary background image for this biome.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: Paths to specific edge images for the background.
*   **`background_edge_priority`**: "12" - Determines the rendering order of background edges.
*   **`wang_template_file`**: "" - Specifies a Wang Tile template file (empty here, suggesting default or script-driven).
*   **`lua_script`**: "data/scripts/biomes/funroom.lua" - The Lua script responsible for dynamic biome generation and behavior.
*   **`wang_map_width`, `wang_map_height`**: "256" - The dimensions of the generated Wang Tile map.
*   **`audio_ambience`**: "temple" - The ambient soundscape associated with this biome.

### BitmapCaves:

This section defines parameters for generating cave-like structures within the biome.

*   **`size_x`, `size_y`**: "256" - The dimensions for cave generation.
*   **`spawn_percent`**: "0" - No direct spawning based on percentage.
*   **`blob_caves_count_min/max`**: "0" to "1" - Controls the number of blob-like cave formations.
*   **`blob_caves_radius_min/max`**: "1" to "1" - Defines the radius of these blob caves.
*   **`blob_caves_strength_min/max`**: "1.2" to "2" - Controls the intensity or depth of blob caves.
*   **`cave_childs_min/max`**: "0" to "1" - Number of smaller cave systems branching off main ones.
*   **`cave_count_min/max`**: "1" to "2" - The number of primary cave systems.
*   **`cave_strength_min/max`**: "0.2" to "1.8" - Intensity of the main cave structures.
*   **`mountain_count_min/max`**: "0" to "0" - No mountains generated.

## Materials

The `Materials` section defines the various substances and objects that make up the biome's terrain and environment.

### Key Material Components:

Each `MaterialComponent` defines a specific material and its properties within the biome.

| Attribute             | Description