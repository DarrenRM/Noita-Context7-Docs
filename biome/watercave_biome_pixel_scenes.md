---
title: Watercave Biome Pixel Scenes
category: biome
---

# Watercave Biome Pixel Scenes

This document details the pixel scene configurations for the Watercave biome in Noita, as defined in `data/biome_impl/spliced/watercave.xml`. Pixel scenes are used to define the visual layout and material composition of specific areas within a biome.

## PixelScene Elements

The `PixelScenes` element contains `mBufferedPixelScenes`, which in turn holds multiple `PixelScene` elements. Each `PixelScene` defines a distinct visual segment of the biome.

### Key Attributes of PixelScene

*   **`material_filename`**: Specifies the `.plz` file containing the material data for this scene. This is the primary definition of the scene's physical properties and appearance.
*   **`background_filename`**: (Optional) Points to a PNG file for the background layer of the scene. If empty, no specific background image is used for this scene.
*   **`colors_filename`**: (Optional) Points to a PNG file that defines the color palette for the scene. If empty, default biome colors are used.
*   **`pos_x`**: The X-coordinate where this scene begins within the biome.
*   **`pos_y`**: The Y-coordinate where this scene begins within the biome.
*   **`skip_biome_checks`**: A flag. When set to `1`, it bypasses standard biome generation checks for this specific scene, allowing for more custom placement and composition.

### Configured Pixel Scenes

| `material_filename`                                | `pos_x` | `pos_y` | `skip_biome_checks` | Notes                                                              |
| :------------------------------------------------- | :------ | :------ | :------------------ | :----------------------------------------------------------------- |
| `data/biome_impl/spliced/watercave/0.plz`          | -2048   | 389     | 1                   | First scene, likely establishing a base layer.                     |
| `data/biome_impl/spliced/watercave/1.plz`          | -2048   | 512     | 1                   | Another scene at a similar X-coordinate, potentially layered.      |
| `data/biome_impl/spliced/watercave/2.plz`          | -2047   | 1027    | 1                   | A scene further down the Y-axis, indicating depth or progression. |

**Note:** The `background_filename` and `colors_filename` are empty for all listed scenes, indicating that the biome's default background and color schemes are applied. The `skip_biome_checks="1"` attribute suggests these scenes are manually placed or have specific generation requirements.