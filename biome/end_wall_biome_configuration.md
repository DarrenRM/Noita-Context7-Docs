---
title: End Wall Biome Configuration
category: biome
---

# End Wall Biome Configuration

This document details the configuration for the "End Wall" biome in Noita, primarily focusing on its topological and material properties. This biome serves as a boundary or a distinct area within the game world.

## Topology

The `<Topology>` element defines the fundamental characteristics of the biome's generation and appearance.

### Key Attributes:

*   **`name`**: `$biome_end_wall` - The internal identifier for this biome.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background image used for this biome.
*   **`background_use_neighbor`**: `0` - Indicates that the background image is not influenced by neighboring biomes.
*   **`lua_script`**: `data/scripts/biomes/end_wall.lua` - The Lua script responsible for dynamic generation or behavior within this biome.
*   **`wang_map_width`**: `256` - The width of the Wang tile map used for terrain generation.
*   **`wang_map_height`**: `256` - The height of the Wang tile map used for terrain generation.
*   **`limit_background_image`**: `0` - Controls whether the background image is limited in its display.
*   **`coarse_map_force_terrain`**: `1` - Forces terrain generation on the coarse map.
*   **`pixel_scene`**: `1` - Enables pixel-based scene generation.
*   **`noise_biome_edges`**: `0` - Disables noise generation at biome edges.
*   **`audio_ambience`**: `temple` - Sets the ambient audio theme for this biome.

## Materials

The `<Materials>` element defines the types and distribution of materials within the biome.

### Key Attributes:

*   **`name`**: `temple` - The identifier for the material set used in this biome.

**Note:** The provided XML snippet includes commented-out `<MaterialComponent>` elements. These would typically define specific materials, their properties (like `is_rare`, `material_index`, `material_min`, `material_max`), and potentially their shape using `<polygon>` data. When uncommented and configured, these components would dictate the physical composition of the biome's terrain.