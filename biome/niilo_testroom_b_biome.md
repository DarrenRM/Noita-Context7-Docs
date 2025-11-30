---
title: Niilo Testroom B Biome
category: biome
---

# Niilo Testroom B Biome

This document describes the configuration for the `niilo_testroom_b.xml` biome in Noita, focusing on its environmental properties and material distribution.

## Topology

The `Topology` element defines the fundamental characteristics of the biome's generation and appearance.

### Key Attributes:

*   **`name`**: `_EMPTY_` - Indicates this is a base biome definition.
*   **`type`**: `BIOME_WANG_TILE` - Specifies that this biome uses Wang tiles for its structure.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Sets the primary background image for the biome.
*   **`background_use_neighbor`**: `0` - The background image does not adapt based on neighboring biomes.
*   **`lua_script`**: `data/scripts/biomes/niilo_testroom_b.lua` - Links a custom Lua script for biome-specific logic.
*   **`wang_map_width`**: `256` - The width of the Wang tile map used for generation.
*   **`wang_map_height`**: `256` - The height of the Wang tile map used for generation.
*   **`coarse_map_force_terrain`**: `1` - Forces terrain generation in the coarse map.
*   **`audio_ambience`**: `cave` - Sets the ambient soundscape to a cave environment.
*   **`noise_biome_edges`**: `0` - Disables noise generation at biome edges.
*   **`skip_edge_textures`**: `1` - Skips applying textures at biome edges.

## Materials

The `Materials` element defines the various materials and vegetation that can spawn within this biome.

### `excavationsite` Material Components:

This section details the distribution and properties of different materials within the `excavationsite` group.

| Attribute              | Value