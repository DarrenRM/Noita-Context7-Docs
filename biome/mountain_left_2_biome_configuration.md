---
title: Mountain Left 2 Biome Configuration
category: biome
---

# Mountain Left 2 Biome Configuration

This document outlines the configuration for the "Mountain Left 2" biome in Noita, focusing on its initialization and visual elements.

## Initialization

The `init` function is responsible for loading the visual components of the biome.

### Key Functions

*   `RegisterSpawnFunction( 0xffffeedd, "init" )`: Registers the `init` function to be called during biome generation. The `0xffffeedd` likely represents a specific biome ID or identifier.
*   `init( x, y, w, h )`: The primary initialization function for this biome.
    *   `x`, `y`, `w`, `h`: These parameters represent the position and dimensions of the biome area being generated.

### Pixel Scene Loading

The `init` function utilizes `LoadPixelScene` to populate the biome with visual data.

*   `LoadPixelScene( "data/biome_impl/mountain/left_bottom.png", "", x, y + 512, "", true )`: Loads a base layer for the biome, likely a foundational ground or structure.
    *   The empty strings (`""`) for material and visual parameters suggest default settings are used.
    *   `y + 512` indicates this layer is positioned below the main biome layer.
    *   `true` likely enables some form of blending or integration.
*   `LoadPixelScene( "data/biome_impl/mountain/left_2.png", "data/biome_impl/mountain/left_2_visual.png", x, y, "", true )`: Loads the primary visual and structural elements of the "Mountain Left 2" biome.
    *   `"data/biome_impl/mountain/left_2.png"`: The main pixel data defining the biome's layout and solid objects.
    *   `"data/biome_impl/mountain/left_2_visual.png"`: The associated visual layer, likely handling effects, lighting, or decorative elements.
    *   `x`, `y`: Position of this layer.
    *   `""`: Default material settings.
    *   `true`: Enables integration.

## Dependencies

This biome configuration relies on several helper scripts:

*   `dofile_once("data/scripts/director_helpers.lua")`: Provides utility functions for managing game directors and biome placement.
*   `dofile_once("data/scripts/biomes/mountain/mountain.lua")`: Imports general configurations and functions related to mountain biomes.

## Constants

*   `CHEST_LEVEL = 3`: This constant likely influences the type or frequency of chests that can spawn within this biome. A value of 3 suggests a mid-tier chest level.