---
title: Wand Cave Biome Configuration
category: guides
---

{
  "title": "Wand Cave Biome Configuration",
  "category": "biome"
}
```

# Wand Cave Biome Configuration

This document details the configuration for the Wand Cave biome in Noita, focusing on its topological generation, material distribution, and environmental elements.

## Topology

The `Topology` element defines the fundamental structure and appearance of the Wand Cave.

### Key Attributes:

*   **`name`**: `$biome_wandcave` - Internal identifier for the biome.
*   **`type`**: `BIOME_WANG_TILE` - Specifies the biome generation method using Wang tiles.
*   **`background_image`**: `data/weather_gfx/background_wandcave.png` - The primary background image for the biome.
*   **`wang_template_file`**: `data/wang_tiles/wand.png` - The image file containing the Wang tiles used for generating the biome's structure.
*   **`lua_script`**: `data/scripts/biomes/wandcave.lua` - The script that governs the biome's dynamic behavior and generation logic.
*   **`wang_map_width` / `wang_map_height`**: `256` - Dimensions of the Wang tile map.
*   **`audio_ambience`**: `wandcave` - The soundscape associated with this biome.

### Bitmap Caves Configuration:

The `BitmapCaves` element controls the procedural generation of cave structures within the biome.

*   **`size_x` / `size_y`**: `516` / `256` - Dimensions of the area where caves can be generated.
*   **`blob_caves_radius_min` / `blob_caves_radius_max`**: `1` / `1` - Controls the size of blob-like cave formations.
*   **`blob_caves_strength_min` / `blob_caves_strength_max`**: `1.2` / `2` - Dictates the intensity or depth of blob caves.
*   **`cave_count_min` / `cave_count_max`**: `1` / `2` - The number of main cave systems to generate.
*   **`cave_strength_min` / `cave_strength_max`**: `0.2` / `1.8` - The intensity or depth of general cave structures.
*   **`mountain_count_min` / `mountain_count_max`**: `0` / `0` - Explicitly disables mountain generation in this biome.

## Materials

The `Materials` element defines the types of materials and vegetation present in the Wand Cave.

### Material Components:

These components specify the distribution and properties of different materials.

| Material Name                 | `is_rare` | `material_index` | `material_min` | `material_max` | `rare_polka_probability` | `rare_scale_x` | `rare_scale_y` |
| :---------------------------- | :-------- | :--------------- | :------------- | :------------- | :----------------------- | :------------- | :------------- |
| `diamond`                     | `1`       | `10`             | `1.1`          | `1.2`          | `0.757143`               | `0.0214286`    | `0.0214286`    |
| `radioactive_liquid`          | `1`       | `10`             | `1.0`          | `1.3`          | `0.3`                    | `0.01`         | `0.04`         |
| `templeslab_crumbling_static` | `0`       | `11`             | `0.00006`      | `3.5`          | `0.2`                    | `0.05`         | `0.05`         |

*   **`limit_max_y` / `limit_min_y`**: These attributes (e.g., `2048` / `100`) define vertical boundaries for material placement.
*   **`rare_use_polka`**: `1` - Indicates that a polka-like distribution pattern is used for rare materials.
*   **`rare_polka_radius_low` / `rare_polka_radius_high`**: Control the clustering of rare materials.

### Vegetation Components:

These define the types of flora that can spawn in the biome.

*   **`vine_growth_1.xml`**:
    *   **`tree_material`**: `ceiling_plant_material`
    *   **`tree_probability`**: `0.24571`
    *   **`is_ceiling_plant`**: `1` (Indicates it grows from the ceiling)
    *   **`visual_color`**: `0x00b89f6c`

*   **`redplant_0$[1-4].xml`**:
    *   **`tree_material`**: `plant_material_red`
    *   **`tree_probability`**: `0.4`
    *   **`is_rare`**: `1`
    *   **`visual_color`**: `0xff4d5d44`

*   **`tree_width`**: Controls the visual width of the vegetation.
*   **`tree_radius_low` / `tree_radius_high`**: Define the radial distribution area for vegetation.