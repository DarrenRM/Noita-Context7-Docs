---
title: Flat Hills Biome Configuration
category: biome
---

# Flat Hills Biome Configuration

This document details the configuration for the "Flat Hills" biome in Noita, focusing on its topographical generation, material distribution, and vegetation.

## Topology Generation

The `Topology` element defines the fundamental shape and environmental characteristics of the biome.

### Key Attributes:

*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background image used for this biome.
*   **`lua_script`**: `data/scripts/biomes/hills.lua` - Links to a Lua script that can further customize biome generation or behavior.
*   **`noise_type`**: `SIN_CAPPED_SIMPLEX` - The type of noise algorithm used for generating terrain variations.
*   **`mGradientAddNoise`**, **`mGradientHighNoise`**, **`mGradientLowNoise`**, **`mGradientNoiseScale`**: These attributes control the influence and scale of noise on the gradient, affecting terrain undulation.
*   **`mGradientEndY`**: `1024` - The Y-coordinate where the gradient effect ends.
*   **`mGradientStartY`**: `-750` - The Y-coordinate where the gradient effect begins.
*   **`mMultiplierGradient`**: `0.871429` - A multiplier applied to the gradient, influencing its overall impact.
*   **`audio_ambience`**: `cave` - The default ambient soundscape for the biome.
*   **`audio_ambience_surface`**: `hills` - A specific ambient soundscape for the surface layer of this biome.

### Bitmap Caves:

The `BitmapCaves` element defines parameters for generating cave systems within the biome.

*   **`name`**: `bitmap_hills` - A descriptive name for this cave generation configuration.
*   **`size_x`**, **`size_y`**: `512`, `256` - The dimensions of the bitmap used for cave generation.
*   **`blob_caves_count_min`**, **`blob_caves_count_max`**: `20`, `55` - The minimum and maximum number of "blob" caves to generate.
*   **`blob_caves_radius_min`**, **`blob_caves_radius_max`**: `1`, `10` - The minimum and maximum radius of these blob caves.
*   **`cave_count_min`**, **`cave_count_max`**: `50`, `100` - The overall minimum and maximum number of caves.
*   **`mountain_count_min`**, **`mountain_count_max`**: `0`, `15` - Controls the generation of mountain-like structures.
*   **`surface_caves_count_min`**, **`surface_caves_count_max`**: `7`, `12` - Defines the number of caves specifically near the surface.

## Material Distribution

The `Materials` element governs the types and distribution of materials within the biome.

### Key Material Components:

The `MaterialComponent` elements define specific materials and their properties.

| Attribute               | Description