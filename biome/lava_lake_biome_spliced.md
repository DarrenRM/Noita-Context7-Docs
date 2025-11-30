---
title: Lava Lake Biome (Spliced)
category: biome
---

# Lava Lake Biome (Spliced)

This documentation describes the configuration for a spliced lava lake biome in Noita, generated from a pixel scene.

## Core Configuration

This biome is defined by a pixel scene that dictates its visual appearance and underlying properties.

### Pixel Scene Definition

*   **`lavalake2.png`**: The primary image file used to define the biome's layout and features. This image is interpreted by `wizard_physics.exe` to generate the biome's structure.
*   **`data/biome_impl/spliced/lavalake2.png`**: The specific path to the pixel scene file.

### Generation Parameters

*   **`-x 2048`**: Sets the width of the generated biome to 2048 pixels.
*   **`-y 0`**: Sets the starting Y-coordinate for the biome generation. In this case, it starts at the very top.

## Generation Process

The biome is generated using a specialized tool that interprets the pixel data.

### Tool Invocation

The following command is used to splice the pixel scene into the game's data:

```bash
pushd ..\..\..\
wizard_physics.exe -splice_pixel_scene data/biome_impl/spliced/lavalake2.png -x 2048 -y 0
popd
```

*   **`wizard_physics.exe`**: The executable responsible for processing and splicing biome data.
*   **`-splice_pixel_scene`**: The command-line argument indicating that a pixel scene should be used for biome generation.

## Key Attributes (Inferred from context)

While the provided data is minimal, the name `lavalake2` and the context of biome generation suggest the following key attributes would be defined within the `lavalake2.png` pixel data or associated configuration files:

*   **Material Composition**: Pixels in `lavalake2.png` would likely map to lava, rock, and potentially other molten or volcanic materials.
*   **Environmental Hazards**: Expect high temperatures, potential for fire, and damaging liquids.
*   **Terrain Features**: The image would define the shape of the lake, islands, and any surrounding rock formations.
*   **Enemy Spawns**: Specific areas might be designated for spawning fire-resistant or lava-dwelling enemies.
*   **Visual Effects**: Associated particle effects for heat distortion, smoke, and bubbling lava would be expected.