---
title: Lava Lake Biome Pixel Scenes
category: biome
---

# Lava Lake Biome Pixel Scenes

This document details the pixel scene configurations for the Lava Lake biome in Noita, as defined in `lavalake.xml`. These scenes are used to construct the visual layout and material distribution of the biome.

## Pixel Scene Definitions

The `<PixelScenes>` element contains a `<mBufferedPixelScenes>` section, which holds multiple `<PixelScene>` definitions. Each `<PixelScene>` defines a specific visual tile or segment of the biome.

### Key Attributes for `<PixelScene>`

*   **`material_filename`**: (Required) Specifies the PNG file containing the material data for this scene. This file dictates what materials (e.g., lava, rock) are present in the scene.
*   **`pos_x`**: The X-coordinate where this scene is placed within the biome's grid.
*   **`pos_y`**: The Y-coordinate where this scene is placed within the biome's grid.
*   **`clean_area_before`**: (Optional) If set to `1`, it indicates that the area should be cleared before this scene is placed, preventing overlapping issues.
*   **`skip_biome_checks`**: (Optional) If set to `1`, biome generation checks are skipped for this specific scene, allowing for more custom placement.
*   **`background_filename`**: (Optional) Path to a background image file for this scene.
*   **`colors_filename`**: (Optional) Path to a color mapping file for this scene.

### Defined Pixel Scenes

The following table lists the key pixel scenes used to construct the Lava Lake biome.

| `material_filename`                                       | `pos_x` | `pos_y` | Description                               |
| :-------------------------------------------------------- | :------ | :------ | :---------------------------------------- |
| `data/biome_impl/spliced/lavalake/lavalake_left_top.png`  | 2018    | 482     | Top-left segment of the lava lake.        |
| `data/biome_impl/spliced/lavalake/lavalake_left_bottom.png`| 2018    | 768     | Bottom-left segment of the lava lake.     |
| `data/biome_impl/spliced/lavalake/lavalake_middle_top.png`| 2560    | 482     | Top-middle segment of the lava lake.      |
| `data/biome_impl/spliced/lavalake/lavalake_middle_bottom.png`| 2560    | 768     | Bottom-middle segment of the lava lake.   |
| `data/biome_impl/spliced/lavalake/lavalake_right_top.png` | 3072    | 482     | Top-right segment of the lava lake.       |
| `data/biome_impl/spliced/lavalake/lavalake_right_bottom.png`| 3072    | 768     | Bottom-right segment of the lava lake.    |
| `data/biome_impl/spliced/lavalake/lavalake_right_bottom_extra.png`| 3584 | 768     | Additional segment to the right bottom.   |
| `data/biome_impl/spliced/lavalake/lavalake_pit_top.png`   | 3584    | 482     | Top segment of a pit within the lake.     |
| `data/biome_impl/spliced/lavalake/lavalake_under.png`     | 2560    | 1536    | Segment located beneath the main lake.    |
| `data/biome_impl/spliced/lavalake/lavalake_under_right.png`| 3072    | 1536    | Right segment located beneath the lake.   |
| `data/biome_impl/spliced/lavalake/lavalake_right_wall.png`| 3072    | 1024    | A wall segment on the right side.         |

These `PixelScene` definitions are crucial for defining the spatial arrangement and material composition of the Lava Lake biome. Modders can leverage these by creating new `material_filename` PNGs to alter the biome's appearance or by adjusting `pos_x` and `pos_y` to change its layout.