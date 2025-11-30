---
title: Moon Dark Biome Pixel Scenes
category: biome
---

# Moon Dark Biome Pixel Scenes

This document describes the pixel scene configurations for the "Moon Dark" biome in Noita, as defined in `moon_dark.xml`. Pixel scenes are used to define visual elements and materials within a biome.

## PixelScenes

The root element for defining pixel scenes.

### mBufferedPixelScenes

Contains a collection of buffered pixel scenes.

#### PixelScene

Defines a specific pixel scene.

*   **background_filename**: `data/biome_impl/spliced/moon_dark/0_background.png`
    *   Specifies the background image file for this scene.
*   **colors_filename**: `data/biome_impl/spliced/moon_dark/0_visual.plz`
    *   Specifies the color palette file for this scene.
*   **material_filename**: `data/biome_impl/spliced/moon_dark/0.plz`
    *   Specifies the material layout file for this scene.
*   **pos_x**: `9`
    *   The X-coordinate position of the scene.
*   **pos_y**: `37513`
    *   The Y-coordinate position of the scene.
*   **skip_biome_checks**: `1`
    *   Indicates that biome checks should be skipped for this scene, allowing it to appear in different biomes.

```xml
<PixelScenes>

  <mBufferedPixelScenes>

    <PixelScene background_filename="data/biome_impl/spliced/moon_dark/0_background.png" colors_filename="data/biome_impl/spliced/moon_dark/0_visual.plz" material_filename="data/biome_impl/spliced/moon_dark/0.plz" pos_x="9" pos_y="37513" skip_biome_checks="1" >

    </PixelScene>

  </mBufferedPixelScenes>

</PixelScenes>
```