---
title: Lake Statue Biome Pixel Scenes
category: biome
---

# Lake Statue Biome Pixel Scenes

This document details the pixel scene configurations for the Lake Statue biome in Noita, as defined in `data/biome_impl/spliced/lake_statue.xml`. These scenes define the visual layout and material placement within specific areas of the biome.

## Pixel Scene Definitions

The `<PixelScenes>` element contains one or more `<mBufferedPixelScenes>` elements, which in turn hold individual `<PixelScene>` definitions. Each `<PixelScene>` represents a distinct visual layer or arrangement within the biome.

### Key Attributes for `PixelScene`

*   **`material_filename`**: Specifies the `.plz` file containing the material data for this scene. This is crucial for defining the blocks and their properties.
*   **`background_filename`**: Points to the PNG file used as the background for this scene.
*   **`pos_x`**, **`pos_y`**: Define the X and Y coordinates where this pixel scene is placed within the biome's world.
*   **`skip_biome_checks`**: A flag that, when set to `1`, bypasses standard biome checks for this scene. This allows for more flexible placement and composition.

### Defined Pixel Scenes

| Scene Index | Material Filename                                     | Background Filename                                   | Position (X, Y) | Skip Biome Checks |
| :---------- | :---------------------------------------------------- | :---------------------------------------------------- | :-------------- | :---------------- |
| 0           | `data/biome_impl/spliced/lake_statue/0.plz`           | `data/biome_impl/spliced/lake_statue/0_background.png` | (-14848, 160)   | 1                 |
| 1           | `data/biome_impl/spliced/lake_statue/1.plz`           | `data/biome_impl/spliced/lake_statue/1_background.png` | (-14336, 23)    | 1                 |
| 2           | `data/biome_impl/spliced/lake_statue/2.plz`           | `data/biome_impl/spliced/lake_statue/2_background.png` | (-13824, 93)    | 1                 |

**Note:** The `colors_filename` attribute is present but empty in these definitions, indicating that color data is likely embedded within the `.plz` files or handled by other means.