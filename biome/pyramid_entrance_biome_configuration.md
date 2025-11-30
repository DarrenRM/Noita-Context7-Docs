---
title: Pyramid Entrance Biome Configuration
category: biome
---

# Pyramid Entrance Biome Configuration

This document details the configuration for the Pyramid Entrance biome in Noita, focusing on key attributes that define its visual appearance, structure, and material composition.

## Topology

The `Topology` element defines the overall shape, background, and noise generation for the biome.

### Key Attributes

| Attribute Name          | Description                                                                                                | Example Value        |
| :---------------------- | :--------------------------------------------------------------------------------------------------------- | :------------------- |
| `name`                  | Internal identifier for the topology.                                                                      | `_EMPTY_`            |
| `background_image`      | Path to the main background image for the biome.                                                           | `data/weather_gfx/background_pyramid.png` |
| `lua_script`            | Path to the Lua script that governs biome-specific behaviors and generation.                               | `data/scripts/biomes/pyramid_entrance.lua` |
| `noise_type`            | The primary noise algorithm used for terrain generation.                                                   | `SIN_CAPPED_SIMPLEX` |
| `mGradientEndY`         | The Y-coordinate where the gradient effect ends.                                                           | `1024`               |
| `mGradientStartY`       | The Y-coordinate where the gradient effect starts.                                                         | `-1024`              |
| `mInsideNoiseType`      | The noise algorithm used for internal details within the biome.                                            | `SimplexNoise1234`   |
| `mInsidePerlinScaleX`   | X-axis scaling factor for Perlin noise used for internal details.                                          | `0.96`               |
| `mInsidePerlinScaleY`   | Y-axis scaling factor for Perlin noise used for internal details.                                          | `0.96`               |
| `audio_ambience`        | The primary ambient sound tag for the biome.                                                               | `temple`             |
| `audio_ambience_surface`| The ambient sound tag for the biome's surface layer.                                                       | `desert`             |
| `has_rain`              | Determines if rain effects are active in this biome.                                                       | `0` (false)          |

### Bitmap Caves

This section defines how cave structures are generated within the biome.

#### Key Attributes

| Attribute Name              | Description                                                                                             | Example Value |
| :-------------------------- | :------------------------------------------------------------------------------------------------------ | :------------ |
| `size_x`                    | Width of the bitmap used for cave generation.                                                           | `512`         |
| `size_y`                    | Height of the bitmap used for cave generation.                                                          | `256`         |
| `blob_caves_count_min`      | Minimum number of "blob" cave formations.                                                               | `5`           |
| `blob_caves_radius_max`     | Maximum radius of "blob" cave formations.                                                               | `10`          |
| `cave_count_min`            | Minimum number of general cave formations.                                                              | `10`          |
| `cave_count_max`            | Maximum number of general cave formations.                                                              | `30`          |
| `surface_caves_count_min`   | Minimum number of cave formations specifically on the surface.                                          | `1`           |
| `surface_caves_count_max`   | Maximum number of cave formations specifically on the surface.                                          | `3`           |

#### Cave Structures

Defines specific types of cave formations and their properties.

| Image File                                  | AABB Min X | AABB Max X | AABB Min Y | AABB Max Y | Count Min | Count Max | Strength Min | Strength Max |
| :------------------------------------------ | :--------- | :--------- | :--------- | :--------- | :-------- | :-------- | :----------- | :----------- |
| `data/biome_impl/caves/mountain_rock.png`   | `5`        | `507`      | `0`        | `20`       | `0`       | `4`       | `1.45`       | `1.55`       |
| `data/biome_impl/caves/pit.png`             | `5`        | `507`      | `-8`       | `2`        | `2`       | `5`       | `0.0`        | `0.65`       |
| `data/biome_impl/caves/deep_pit.png`        | `5`        | `507`      | `-8`       | `2`        | `5`       | `8`       | `0.0`        | `0.40`       |
| `data/biome_impl/caves/brush_03.png`        | `5`        | `507`      | `0`        | `15`       | `0`       | `3`       | `1.15`       | `1.85`       |
| `data/biome_impl/caves/brush_04.png`        | `5`        | `507`      | `0`        | `15`       | `0`       | `4`       | `0.5`        | `2.85`       |
| `data/biome_impl/caves/brush_05.png`        | `5`        | `507`      | `0`        | `25`       | `0`       | `3`       | `0.15`       | `2.15`       |
| `data/biome_impl/caves/brush_06.png`        | `5`        | `507`      | `0`        | `35`       | `0`       | `4`       | `0.55`       | `1.85`       |

## Materials

The `Materials` element defines the different material components that make up the biome and their distribution.

### Key Attributes

| Attribute Name | Description