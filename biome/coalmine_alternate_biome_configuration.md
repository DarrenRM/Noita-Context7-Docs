---
title: Coalmine Alternate Biome Configuration
category: biome
---

# Coalmine Alternate Biome Configuration

This document details the configuration for the alternate Coalmine biome in Noita, focusing on its environmental properties, material distribution, and vegetation.

## Topology

The `Topology` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes

| Attribute | Description |
|---|---|
| `name` | Internal name for the biome: `$biome_coalmine_alt`. |
| `type` | Biome generation type: `BIOME_WANG_TILE`. |
| `background_image` | Path to the main background image: `data/weather_gfx/background_coalmine.png`. |
| `wang_template_file` | Specifies the Wang tile template used for generation: `data/wang_tiles/coalmine_alt.png`. |
| `lua_script` | Associated Lua script for biome logic: `data/scripts/biomes/coalmine_alt.lua`. |
| `wang_map_width` | Width of the Wang map: `256`. |
| `wang_map_height` | Height of the Wang map: `256`. |
| `audio_music_2` | Music track associated with the biome: `coalmine`. |
| `audio_ambience` | Ambience sound for the biome: `wandcave`. |

### Bitmap Caves

This section defines parameters for generating cave structures within the biome.

| Attribute | Description |
|---|---|
| `size_x` | Width of the cave generation area: `512`. |
| `size_y` | Height of the cave generation area: `256`. |
| `cave_childs_max` | Maximum number of child caves: `1`. |
| `cave_count_min` | Minimum number of main caves: `2`. |
| `cave_count_max` | Maximum number of main caves: `2`. |
| `cave_strength_min` | Minimum strength of caves: `0.2`. |
| `cave_strength_max` | Maximum strength of caves: `1`. |

#### Structures

Defines specific structures to be placed within caves.

*   **Danger Room:**
    *   `image_file`: `data/biome_impl/coalmine/dangerroom.png`
    *   `aabb_min_x`: `5`
    *   `aabb_max_x`: `507`
    *   `aabb_min_y`: `0`
    *   `aabb_max_y`: `230`
    *   `count_min`: `2`
    *   `count_max`: `4`
    *   `strength_min`: `1.45`
    *   `strength_max`: `1.55`

## Materials

The `Materials` element governs the distribution and properties of various materials within the biome.

### Key Material Components

| Material Name | Rarity | Y-Limits (min/max) | Material Range (min/max) | Polka Probability | Scale (X/Y) | Use Perlin | Use Polka |
|---|---|---|---|---|---|---|---|
| `coal` | Rare | 100/2048 | 0.51/0.55 | 0.160871 | 0.0100004/0.00357165 | 0 | 1 |
| `soil` | Common | -1024/424.229 | 0.45/0.53 | 0.2 | 0.05/0.05 | 0 | 1 |
| `sand_static` | Common | 100/2048 | 0.53/0.95 | 0.2 | 0.05/0.05 | 0 | 1 |
| `coal` (Rare variant) | Rare | 100/2048 | 1.1/1.2 | 0.157143 | 0.0214286/0.0214286 | 1 | 1 |
| `copper` | Rare | 750/2048 | 1.05/1.25 | 0.357143 | 0.007514286/0.007514286 | 1 | 1 |
| `gold` | Rare | 750/2048 | 1.05/1.2 | 0.357143 | 0.027514286/0.057514286 | 1 | 1 |
| `rock_static_wet` | Common | 100/2048 | 0.9/3.5 | 0.2 | 0.05/0.05 | 0 | 1 |

*   **Note:** `material_index` is consistently `10` for most materials, indicating their layer or depth. `rare_polka_is_boxed` and `rare_required_max`/`rare_required_min` influence the clustering and density of rare materials.

## Vegetation

This section defines the types of vegetation that can spawn in the biome.

### Key Vegetation Components

| Component Type | Visual | Material | Probability | Radius (Low/High) | Width | Visual Color | Offset (X/Y) | Special Properties |
|---|---|---|---|---|---|---|---|---|
| `grass` | Yes | `grass` | 0.828571 | 0.228571/0.414286 | 76.1143 | `0xffb89f6c` | 3/7.5 | `grass_requires_neighbors="0"`, `material_on_top_of="soil"` |
| `grass` | Yes | `grass` | 0.828571 | 0.228571/0.414286 | 76.1143 | `0xffb89f6c` | 3/7.5 | `grass_requires_neighbors="1"`, `material_on_top_of="sand_static"` |
| `ceiling_plant` | Yes | `ceiling_plant_material` | 0.24571 | 0.146757/0.635286 | 110.123 | `0x00b89f6c` | 3/0 | `tree_image_file="data/vegetation/vine_growth_1.xml"` |
| `ceiling_plant` | Yes | `ceiling_plant_material` | 0.54571 | 0.146757/0.635286 | 11.123 | `0x00b89f6c` | 3/1 | `tree_image_file="data/vegetation/aerial_root_$[1-9].png"` |
| `mushroom_small` | No | `fungus_loose` | 0.128571 | 0.328571/0.414286 | 18.1143 | `0xffb89f6c` | 3/1 | `material_on_top_of="sand_static"` |
| `mushroom_small` | No | `fungus_loose` | 0.128571 | 0.328571/0.414286 | 16.1143 | `0xffb89f6c` | 3/1 | `material_on_top_of="sand_static"` |
| `grass_patch` | Yes | `plant_material` | 0.328571 | 0.1027/0.154286 | 20 | `0xff4d5d44` | 15/32 | `material_on_top_of="soil"` |
| `grass_patch` | Yes | `plant_material` | 0.468571 | 0.1027/0.154286 | 20 | `0xff4d5d44` | 15/32 | `material_on_top_of="sand_static"` |

*   `rand_seed` influences the randomness of placement.
*   `tree_extra_y` adjusts the vertical placement of vegetation.
*   `visual_color` uses ARGB hex format.
*   `is_visual` determines if the vegetation is purely cosmetic or has gameplay implications.
*   `is_grass` and `is_ceiling_plant` are flags for specific vegetation types.