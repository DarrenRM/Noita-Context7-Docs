---
title: Biome Map Configuration
category: scripts
---

# Biome Map Configuration

This script defines the configuration and loading of the game's biome map, allowing for easier modification by mods.

## Core Functionality

The primary purpose of this script is to:

*   **Set Biome Map Dimensions:** Define the grid size of the biome map.
*   **Load Biome Map Image:** Specify the image file that visually represents the biome map.

## Key Attributes

### `BiomeMapSetSize(width, height)`

*   **Description:** Sets the dimensions of the biome map grid.
*   **Parameters:**
    *   `width` (number): The width of the biome map in grid units.
    *   `height` (number): The height of the biome map in grid units.

### `BiomeMapLoadImage(x, y, image_path)`

*   **Description:** Loads an image to be used as the biome map. This image dictates the placement and type of biomes within the game world.
*   **Parameters:**
    *   `x` (number): The starting X-coordinate on the biome map grid where the image will be placed.
    *   `y` (number): The starting Y-coordinate on the biome map grid where the image will be placed.
    *   `image_path` (string): The file path to the biome map image (e.g., `"data/biome_impl/biome_map.png"`).

## Example Usage

```lua
-- Set the biome map to be 70 grid units wide and 48 grid units tall.
BiomeMapSetSize( 70, 48 )

-- Load the biome map image from the specified path, starting at grid coordinates (0, 0).
BiomeMapLoadImage( 0, 0, "data/biome_impl/biome_map.png" )
```