---
title: Tree Biome Pixel Scenes
category: biome
---

# Tree Biome Pixel Scenes

This document describes the `PixelScene` elements used to construct the "Tree" biome in Noita. These scenes define the visual and material layers that make up different parts of the biome.

## PixelScene Elements

The `PixelScene` element defines a specific visual and material layer within a biome. Multiple `PixelScene` elements are used to create the complex environments found in Noita.

### Key Attributes

*   **`background_filename`**: Specifies the PNG file for the background layer of the scene. This provides the base visual appearance.
*   **`colors_filename`**: Points to a `.plz` file containing color data. This file likely defines how colors are applied or modified for the scene.
*   **`material_filename`**: Indicates a `.plz` file that defines the materials present in this scene. This determines the physical properties and interactions of the pixels.
*   **`pos_x`**: The X-coordinate where this scene is placed within the biome.
*   **`pos_y`**: The Y-coordinate where this scene is placed within the biome.
*   **`skip_biome_checks`**: A flag (set to "1" here) that likely bypasses certain biome generation checks for this specific scene, allowing for more custom placement or composition.

### Scene Definitions

The following table lists the defined `PixelScene` elements and their key attributes.

| Background Filename                               | Colors Filename                               | Material Filename                               | Pos X  | Pos Y  | Skip Biome Checks |
| :------------------------------------------------ | :-------------------------------------------- | :---------------------------------------------- | :----- | :----- | :---------------- |
| `data/biome_impl/spliced/tree/0_background.png`   | `data/biome_impl/spliced/tree/0_visual.plz`   | `data/biome_impl/spliced/tree/0.plz`            | -2016  | -1324  | 1                 |
| `data/biome_impl/spliced/tree/1_background.png`   | `data/biome_impl/spliced/tree/1_visual.plz`   | `data/biome_impl/spliced/tree/1.plz`            | -2035  | -812   | 1                 |
| `data/biome_impl/spliced/tree/2_background.png`   | `data/biome_impl/spliced/tree/2_visual.plz`   | `data/biome_impl/spliced/tree/2.plz`            | -2048  | -300   | 1                 |
| `data/biome_impl/spliced/tree/3_background.png`   | `data/biome_impl/spliced/tree/3_visual.plz`   | `data/biome_impl/spliced/tree/3.plz`            | -2048  | 212    | 1                 |
| `data/biome_impl/spliced/tree/4_background.png`   | `data/biome_impl/spliced/tree/4_visual.plz`   | `data/biome_impl/spliced/tree/4.plz`            | -1536  | -1323  | 1                 |
| `data/biome_impl/spliced/tree/5_background.png`   | `data/biome_impl/spliced/tree/5_visual.plz`   | `data/biome_impl/spliced/tree/5.plz`            | -1536  | -812   | 1                 |
| `data/biome_impl/spliced/tree/6_background.png`   | `data/biome_impl/spliced/tree/6_visual.plz`   | `data/biome_impl/spliced/tree/6.plz`            | -1536  | -300   | 1                 |
| `data/biome_impl/spliced/tree/7_background.png`   | `data/biome_impl/spliced/tree/7_visual.plz`   | `data/biome_impl/spliced/tree/7.plz`            | -1536  | 212    | 1                 |

*(Note: The `mBufferedPixelScenes` element acts as a container for these individual `PixelScene` definitions.)*