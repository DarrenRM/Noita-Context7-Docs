---
title: The End Biome Configuration
category: biome
---

# The End Biome Configuration

This document details the configuration for "The End" biome in Noita, focusing on its visual and material properties.

## Topology

The `Topology` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes

| Attribute | Description |
|---|---|
| `name` | Internal identifier for the biome: `$biome_boss_victoryroom`. |
| `type` | Type of biome generation: `BIOME_WANG_TILE`. |
| `background_image` | Path to the main background image. |
| `background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom` | Paths to images used for background edges, creating seamless transitions. |
| `background_edge_priority` | Determines the rendering order of background edges. |
| `wang_template_file` | Path to the Wang tile image used for generating the biome's structure. |
| `lua_script` | Path to the Lua script that governs biome-specific behaviors and generation. |
| `wang_map_width`, `wang_map_height` | Dimensions of the Wang tile map used for generation. |
| `audio_music_2` | Name of the music track associated with this biome. |
| `audio_ambience` | Name of the ambient soundscape for this biome. |

### BitmapCaves

This section controls the generation of cave structures within the biome.

| Attribute | Description |
|---|---|
| `size_x`, `size_y` | Dimensions of the cave generation area. |
| `blob_caves_count_min`, `blob_caves_count_max` | Minimum and maximum number of blob caves. |
| `cave_childs_min`, `cave_childs_max` | Minimum and maximum number of child caves. |
| `cave_count_min`, `cave_count_max` | Minimum and maximum number of main caves. |
| `cave_strength_min`, `cave_strength_max` | Controls the thickness/density of cave walls. |
| `mountain_count_min`, `mountain_count_max` | Minimum and maximum number of mountains. |
| `surface_caves_count_min`, `surface_caves_count_max` | Minimum and maximum number of surface caves. |
| `spawn_percent` | Percentage chance for caves to spawn. |

## Materials

The `Materials` element defines the different materials present in the biome and their properties.

### Material Components

Each `MaterialComponent` defines a specific material and how it's distributed.

#### Coal (Rare)

This component defines the rare distribution of coal.

| Attribute | Description |
|---|---|
| `_enabled` | Whether this component is active. |
| `is_rare` | Indicates if this material is rare. |
| `limit_max_y`, `limit_min_y`, `limit_y` | Vertical limits for material placement. |
| `material_index` | Internal index for the material. |
| `material_max`, `material_min` | Maximum and minimum density of the material. |
| `material_name` | Name of the material: `coal`. |
| `rare_polka_is_boxed` | Whether rare elements are confined to specific areas. |
| `rare_polka_probability` | Probability of a rare element appearing. |
| `rare_polka_radius_high`, `rare_polka_radius_low` | Radius for the polka distribution of rare elements. |
| `rare_required_max`, `rare_required_min` | Minimum/maximum density required for rare placement. |
| `rare_scale_x`, `rare_scale_y` | Scaling factors for the rare distribution pattern. |
| `rare_use_perlin` | Whether Perlin noise is used for distribution. |
| `rare_use_polka` | Whether a polka distribution pattern is used. |

#### Skullrock (Standard)

This component defines the standard distribution of skullrock.

| Attribute | Description |
|---|---|
| `_enabled` | Whether this component is active. |
| `is_rare` | Indicates if this material is rare. |
| `limit_max_y`, `limit_min_y`, `limit_y` | Vertical limits for material placement. |
| `material_index` | Internal index for the material. |
| `material_max`, `material_min` | Maximum and minimum density of the material. |
| `material_name` | Name of the material: `skullrock`. |

#### Coal (Rare, Perlin/Polka)

This component defines another rare distribution of coal, utilizing both Perlin noise and polka patterns.

| Attribute | Description |
|---|---|
| `_enabled` | Whether this component is active. |
| `is_rare` | Indicates if this material is rare. |
| `limit_max_y`, `limit_min_y`, `limit_y` | Vertical limits for material placement. |
| `material_index` | Internal index for the material. |
| `material_max`, `material_min` | Maximum and minimum density of the material. |
| `material_name` | Name of the material: `coal`. |
| `rare_polka_is_boxed` | Whether rare elements are confined to specific areas. |
| `rare_polka_probability` | Probability of a rare element appearing. |
| `rare_polka_radius_high`, `rare_polka_radius_low` | Radius for the polka distribution of rare elements. |
| `rare_required_max`, `rare_required_min` | Minimum/maximum density required for rare placement. |
| `rare_scale_x`, `rare_scale_y` | Scaling factors for the rare distribution pattern. |
| `rare_use_perlin` | Whether Perlin noise is used for distribution. |
| `rare_use_polka` | Whether a polka distribution pattern is used. |

#### Lava (Rare)

This component defines the rare distribution of lava.

| Attribute | Description |
|---|---|
| `_enabled` | Whether this component is active. |
| `is_rare` | Indicates if this material is rare. |
| `limit_max_y`, `limit_min_y`, `limit_y` | Vertical limits for material placement. |
| `material_index` | Internal index for the material. |
| `material_max`, `material_min` | Maximum and minimum density of the material. |
| `material_name` | Name of the material: `lava`. |
| `rare_polka_is_boxed` | Whether rare elements are confined to specific areas. |
| `rare_polka_probability` | Probability of a rare element appearing. |
| `rare_polka_radius_high`, `rare_polka_radius_low` | Radius for the polka distribution of rare elements. |
| `rare_required_max`, `rare_required_min` | Minimum/maximum density required for rare placement. |
| `rare_scale_x`, `rare_scale_y` | Scaling factors for the rare distribution pattern. |
| `rare_use_perlin` | Whether Perlin noise is used for distribution. |
| `rare_use_polka` | Whether a polka distribution pattern is used. |

#### The End (Standard)

This component defines the standard distribution of the biome's namesake material.

| Attribute | Description |
|---|---|
| `_enabled` | Whether this component is active. |
| `is_rare` | Indicates if this material is rare. |
| `limit_max_y`, `limit_min_y`, `limit_y` | Vertical limits for material placement. |
| `material_index` | Internal index for the material. |
| `material_max`, `material_min` | Maximum and minimum density of the material. |
| `material_name` | Name of the material: `the_end`. |
| `add_perlin` | Whether Perlin noise is added to the material's distribution. |
| `add_perlin_scale_y`, `add_perlin_scale_x` | Scaling factors for the added Perlin noise. |

### Vegetation Component

This component defines the visual elements, such as plants, that appear in the biome.

| Attribute | Description |
|---|---|
| `_enabled` | Whether this component is active. |
| `is_visual` | Indicates if this is a visual-only element. |
| `rand_seed` | Seed for random number generation for this component. |
| `tree_extra_y` | Vertical offset for vegetation. |
| `tree_image_file` | Path to the image file for the vegetation. |
| `tree_image_visual` | Path to a visual-only image file for the vegetation. |
| `tree_material` | The material associated with this vegetation. |
| `tree_probability` | Probability of this vegetation appearing. |
| `tree_radius_high`, `tree_radius_low` | Radius for placement of vegetation. |
| `tree_width` | Width of the vegetation. |
| `visual_color` | Color tint for the visual element (RGBA hex). |
| `visual_offset_x`, `visual_offset_y` | Offset for the visual element's position. |