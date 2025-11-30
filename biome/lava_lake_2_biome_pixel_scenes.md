---
title: Lava Lake 2 Biome Pixel Scenes
category: biome
---

# Lava Lake 2 Biome Pixel Scenes

This document details the pixel scene definitions for the "Lava Lake 2" biome in Noita. Pixel scenes are used to define the visual layout and material composition of specific areas within a biome.

## PixelScene Elements

The `PixelScenes` element contains one or more `mBufferedPixelScenes` elements, which in turn hold individual `PixelScene` definitions.

### Key Attributes of `PixelScene`

*   **`material_filename`**: (Required) Specifies the path to the `.plz` file that defines the pixel data for this scene. These `.plz` files contain the actual material and color information for the scene.
*   **`pos_x`**: The X-coordinate where this pixel scene will be placed within the biome.
*   **`pos_y`**: The Y-coordinate where this pixel scene will be placed within the biome.
*   **`skip_biome_checks`**: A flag. When set to `1`, it bypasses certain biome generation checks, allowing for more precise placement or unique scene compositions.

### Defined Pixel Scenes

The following table lists the `PixelScene` elements defined in this file, along with their key attributes.

| `material_filename`                               | `pos_x` | `pos_y` | `skip_biome_checks` |
| :------------------------------------------------ | :------ | :------ | :------------------ |
| `data/biome_impl/spliced/lavalake2/0.plz`         | 2050    | 445     | 1                   |
| `data/biome_impl/spliced/lavalake2/1.plz`         | 2048    | 512     | 1                   |
| `data/biome_impl/spliced/lavalake2/2.plz`         | 2065    | 1024    | 1                   |
| `data/biome_impl/spliced/lavalake2/3.plz`         | 2326    | 1536    | 1                   |
| `data/biome_impl/spliced/lavalake2/4.plz`         | 2556    | 2048    | 1                   |
| `data/biome_impl/spliced/lavalake2/5.plz`         | 2560    | 451     | 1                   |
| `data/biome_impl/spliced/lavalake2/6.plz`         | 2560    | 512     | 1                   |
| `data/biome_impl/spliced/lavalake2/7.plz`         | 2560    | 1024    | 1                   |
| `data/biome_impl/spliced/lavalake2/8.plz`         | 2560    | 1536    | 1                   |
| `data/biome_impl/spliced/lavalake2/9.plz`         | 2560    | 2048    | 1                   |
| `data/biome_impl/spliced/lavalake2/10.plz`        | 3072    | 451     | 1                   |
| `data/biome_impl/spliced/lavalake2/11.plz`        | 3072    | 512     | 1                   |
| `data/biome_impl/spliced/lavalake2/12.plz`        | 3072    | 1024    | 1                   |
| `data/biome_impl/spliced/lavalake2/13.plz`        | 3072    | 1536    | 1                   |
| `data/biome_impl/spliced/lavalake2/14.plz`        | 3072    | 2048    | 1                   |
| `data/biome_impl/spliced/lavalake2/15.plz`        | 3584    | 445     | 1                   |
| `data/biome_impl/spliced/lavalake2/16.plz`        | 3584    | 512     | 1                   |
| `data/biome_impl/spliced/lavalake2/17.plz`        | 3584    | 1024    | 1                   |
| `data/biome_impl/spliced/lavalake2/18.plz`        | 3584    | 1536    | 1                   |
| `data/biome_impl/spliced/lavalake2/19.plz`        | 3584    | 2048    | 1                   |
| `data/biome_impl/spliced/lavalake2/20.plz`        | 4096    | 461     | 1                   |
| `data/biome_impl/spliced/lavalake2/21.plz`        | 4096    | 512     | 1                   |
| `data/biome_impl/spliced/lavalake2/22.plz`        | 4096    | 1024    | 1                   |
| `data/biome_impl/spliced/lavalake2/23.plz`        | 4608    | 2048    | 1                   |
| `data/biome_impl/spliced/lavalake2/24.plz`        | 4608    | 2392    | 1                   |

## Modding Considerations

*   **Customization**: To modify the appearance or composition of the Lava Lake 2 biome, you would typically create or edit the `.plz` files referenced by `material_filename`. These files contain the actual pixel data.
*   **Placement**: The `pos_x` and `pos_y` attributes determine where these pre-defined scenes are placed within the larger biome generation. Adjusting these can alter the layout.
*   **`skip_biome_checks`**: Using `skip_biome_checks="1"` can be useful for creating unique or non-standard arrangements of these scenes, but it might also lead to unexpected generation results if not used carefully.