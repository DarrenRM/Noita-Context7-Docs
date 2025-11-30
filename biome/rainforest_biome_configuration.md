---
title: Rainforest Biome Configuration
category: biome
---

# Rainforest Biome Configuration

This document details the configuration for the Rainforest biome in Noita, focusing on its generation parameters, material distribution, and vegetation.

## Topology Settings

The `Topology` element defines the fundamental generation characteristics of the biome.

### Key Attributes

| Attribute Name              | Description                                                                                                | Example Value        |
| :-------------------------- | :--------------------------------------------------------------------------------------------------------- | :------------------- |
| `name`                      | Internal identifier for the biome.                                                                         | `$biome_rainforest`  |
| `type`                      | Type of biome generation (Wang tiles).                                                                     | `BIOME_WANG_TILE`    |
| `background_image`          | Path to the main background image for the biome.                                                           | `data/weather_gfx/...` |
| `wang_template_file`        | Path to the Wang tile template image used for generation.                                                  | `data/wang_tiles/...`  |
| `lua_script`                | Path to the Lua script that controls biome-specific logic.                                                 | `data/scripts/biomes/...` |
| `mCaveOpenness`             | Controls how open the caves generated within the biome are.                                                | `0.25`               |
| `mCavePerlinNoise`          | Base value for Perlin noise used in cave generation.                                                       | `0.275`              |
| `mGradientHighNoise`        | Higher bound for gradient noise, influencing terrain shape.                                                | `234.057`            |
| `mGradientLowNoise`         | Lower bound for gradient noise, influencing terrain shape.                                                 | `-292.571`           |
| `mMultiplierGradient`       | Multiplier for gradient noise effects.                                                                     | `0.871429`           |
| `audio_music_2`             | Name of the music track to play in this biome.                                                             | `rainforest`         |
| `audio_ambience`            | Name of the ambient soundscape for this biome.                                                             | `rainforest`         |

### Cave Generation Parameters

These attributes fine-tune the procedural generation of caves within the biome.

| Attribute Name             | Description                                                              | Example Value |
| :------------------------- | :----------------------------------------------------------------------- | :------------ |
| `mCaveType`                | Type of cave generation algorithm.                                       | `1`           |
| `mCavePerlinDisplacement`  | Displacement value for Perlin noise in cave generation.                  | `5`           |
| `mCaveStartValue`          | Starting threshold for cave generation.                                  | `0.65`        |
| `mExtraPerlinScaleX`       | Scaling factor for extra Perlin noise on the X-axis.                     | `0.05`        |
| `mExtraPerlinScaleY`       | Scaling factor for extra Perlin noise on the Y-axis.                     | `0.0342857`   |

### Gradient and Noise Parameters

These control the overall shape and texture of the biome's terrain.

| Attribute Name          | Description                                                              | Example Value |
| :---------------------- | :----------------------------------------------------------------------- | :------------ |
| `mGradientType`         | Type of gradient used for terrain shaping.                               | `1`           |
| `mGradientAddNoise`     | Whether to add noise to the gradient.                                    | `1`           |
| `mGradientNoiseScale`   | Scaling factor for gradient noise.                                       | `0.00128571`  |
| `mGradientSinMultipleMax` | Maximum multiplier for sine wave influence on gradient.                  | `0.005153`    |
| `mGradientSinMultipleMin` | Minimum multiplier for sine wave influence on gradient.                  | `0.0021`      |

### Bitmap Caves

This section is currently configured to disable blob caves and mountains, suggesting a focus on more standard cave generation.

| Attribute Name        | Description                               | Example Value |
| :-------------------- | :---------------------------------------- | :------------ |
| `blob_caves_count_min` | Minimum number of blob caves.             | `0`           |
| `mountain_count_min`  | Minimum number of mountains.              | `0`           |

## Material Distribution

The `Materials` element defines the types of materials present in the biome and their distribution.

### Key Material Components

| Material Name             | Rarity | Min/Max Y Limit | Material Min/Max Value | Description