---
title: Boss Arena Pixel Scenes
category: biome
---

# Boss Arena Pixel Scenes

This document details the `PixelScene` definitions for the Boss Arena biome in Noita. These scenes define the visual and material layouts of different sections within the arena.

## PixelScene Elements

Each `PixelScene` element represents a distinct visual chunk of the biome.

### Key Attributes

*   **`background_filename`**: Specifies the path to the background image for this scene.
*   **`material_filename`**: Specifies the path to the `.plz` file containing the material data for this scene. This defines the actual blocks and their properties.
*   **`colors_filename`**: (Optional) Specifies the path to a `.plz` file that defines color variations or palettes for the scene. If absent, default colors are used.
*   **`pos_x`**: The X-coordinate where this scene is placed in the world.
*   **`pos_y`**: The Y-coordinate where this scene is placed in the world.
*   **`clean_area_before`**: If set to `1`, the game will clear any existing pixels in this area before loading the scene. This is crucial for ensuring a clean slate for each scene.
*   **`skip_biome_checks`**: If set to `1`, the game will bypass standard biome generation checks for this scene. This allows for more custom placement and content.
*   **`DEBUG_RELOAD_ME`**: A debug attribute, typically set to `1` to facilitate easier reloading of this specific scene during development.

### Scene Definitions

The following table summarizes the defined `PixelScene` elements. Each entry represents a distinct part of the Boss Arena.

| Scene Index | Background Filename                                     | Colors Filename                                         | Material Filename                                       | Position (X, Y) |
| :---------- | :------------------------------------------------------ | :------------------------------------------------------ | :------------------------------------------------------ | :-------------- |
| 0           | `data/biome_impl/spliced/boss_arena/0_background.png`   | (None)                                                  | `data/biome_impl/spliced/boss_arena/0.plz`              | (1536, 12288)   |
| 1           | `data/biome_impl/spliced/boss_arena/1_background.png`   | `data/biome_impl/spliced/boss_arena/1_visual.plz`       | `data/biome_impl/spliced/boss_arena/1.plz`              | (1536, 12800)   |
| 2           | `data/biome_impl/spliced/boss_arena/2_background.png`   | (None)                                                  | `data/biome_impl/spliced/boss_arena/2.plz`              | (1536, 13312)   |
| 3           | `data/biome_impl/spliced/boss_arena/3_background.png`   | (None)                                                  | `data/biome_impl/spliced/boss_arena/3.plz`              | (1536, 13824)   |
| 4           | `data/biome_impl/spliced/boss_arena/4_background.png`   | (None)                                                  | `data/biome_impl/spliced/boss_arena/4.plz`              | (2048, 12288)   |
| 5           | `data/biome_impl/spliced/boss_arena/5_background.png`   | `data/biome_impl/spliced/boss_arena/5_visual.plz`       | `data/biome_impl/spliced/boss_arena/5.plz`              | (2048, 12800)   |
| 6           | `data/biome_impl/spliced/boss_arena/6_background.png`   | (None)                                                  | `data/biome_impl/spliced/boss_arena/6.plz`              | (2048, 13312)   |
| 7           | `data/biome_impl/spliced/boss_arena/7_background.png`   | (None)                                                  | `data/biome_impl/spliced/boss_arena/7.plz`              | (2048, 13824)   |
| 8           | `data/biome_impl/spliced/boss_arena/8_background.png`   | (None)                                                  | `data/biome_impl/spliced/boss_arena/8.plz`              | (2560, 12288)   |
| 9           | `data/biome_impl/spliced/boss_arena/9_background.png`   | `data/biome_impl/spliced/boss_arena/9_visual.plz`       | `data/biome_impl/spliced/boss_arena/9.plz`              | (2560, 12800)   |
| 10          | `data/biome_impl/spliced/boss_arena/10_background.png`  | `data/biome_impl/spliced/boss_arena/10_visual.plz`      | `data/biome_impl/spliced/boss_arena/10.plz`             | (2560, 13312)   |
| 11          | `data/biome_impl/spliced/boss_arena/11_background.png`  | (None)                                                  | `data/biome_impl/spliced/boss_arena/11.plz`             | (2560, 13824)   |
| 12          | `data/biome_impl/spliced/boss_arena/12_background.png`  | (None)                                                  | `data/biome_impl/spliced/boss_arena/12.plz`             | (3072, 12288)   |
| 13          | `data/biome_impl/spliced/boss_arena/13_background.png`  | `data/biome_impl/spliced/boss_arena/13_visual.plz`      | `data/biome_impl/spliced/boss_arena/13.plz`             | (3072, 12800)   |
| 14          | `data/biome_impl/spliced/boss_arena/14_background.png`  | (None)                                                  | `data/biome_impl/spliced/boss_arena/14.plz`             | (3072, 13312)   |
| 15          | `data/biome_impl/spliced/boss_arena/15_background.png`  | (None)                                                  | `data/biome_impl/spliced/boss_arena/15.plz`             | (3072, 13824)   |
| 16          | `data/biome_impl/spliced/boss_arena/16_background.png`  | (None)                                                  | `data/biome_impl/spliced/boss_arena/16.plz`             | (3584, 12288)   |
| 17          | `data/biome_impl/spliced/boss_arena/17_background.png`  | `data/biome_impl/spliced/boss_arena/17_visual.plz`      | `data/biome_impl/spliced/boss_arena/17.plz`             | (3584, 12800)   |
| 18          | `data/biome_impl/spliced/boss_arena/18_background.png`  | `data/biome_impl/spliced/boss_arena/18_visual.plz`      | `data/biome_impl/spliced/boss_arena/18.plz`             | (3584, 13312)   |
| 19          | `data/biome_impl/spliced/boss_arena/19_background.png`  | (None)                                                  | `data/biome_impl/spliced/boss_arena/19.plz`             | (3584, 13824)   |
| 20          | `data/biome_impl/spliced/boss_arena/20_background.png`  | (None)                                                  | `data/biome_impl/spliced/boss_arena/20.plz`             | (4096, 12288)   |
| 21          | `data/biome_impl/spliced/boss_arena/21_background.png`  | (None)                                                  | `data/biome_impl/spliced/boss_arena/21.plz`             | (4096, 12800)   |
| 22          | `data/biome_impl/spliced/boss_arena/22_background.png`  | (None)                                                  | `data/biome_impl/spliced/boss_arena/22.plz`             | (4096, 13312)   |
| 23          | `data/biome_impl/spliced/boss_arena/23_background.png`  | (None)                                                  | `data/biome_impl/spliced/boss_arena/23.plz`             | (4096, 13824)   |

---