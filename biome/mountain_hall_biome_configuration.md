---
title: Mountain Hall Biome Configuration
category: biome
---

# Mountain Hall Biome Configuration

This file defines the configuration for the "Mountain Hall" biome in Noita, focusing on its visual elements, entity spawning, and interactive components. It acts as a blueprint for how this specific area of the game world is constructed and populated.

## Core Biome Initialization

The `init` function is the primary entry point for setting up the Mountain Hall biome. It handles loading the visual assets and defining the layout of the area.

### Key Initialization Functions:

*   **`LoadPixelScene(filepath, visual_filepath, x, y, background_filepath, is_background)`**: This function is extensively used to load the various visual layers and background elements that constitute the Mountain Hall. It defines the terrain, visual details, and background imagery.
    *   Conditional loading based on `GameGetIsGamepadConnected()` is used to adapt visual elements for different input methods.
*   **`load_verlet_rope_with_two_joints(...)`**: Loads pre-defined verlet rope entities, likely representing vines or similar hanging structures, with specific anchor points.
*   **`load_verlet_rope_with_one_joint(...)`**: Similar to the above, but for shorter verlet rope entities.

## Entity Spawning and Triggers

This section details how various entities and interactive elements are spawned within the Mountain Hall biome, often triggered by specific pixel colors in the biome's definition.

### Spawn Functions:

*   **`RegisterSpawnFunction(pixel_color, function_name)`**: This is a crucial mechanism for associating specific pixel colors within the biome's `*.png` files with corresponding Lua functions that will spawn entities or trigger events at those locations.

### Key Spawn Functions and their Purpose:

| Function Name        | Associated Pixel Color | Description