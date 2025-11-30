---
title: Town Under Biome
category: biome
---

# Town Under Biome

This document details the configuration for the "Town Under" biome in Noita, focusing on its visual and material properties.

## Topology

The `Topology` element defines the fundamental structure and appearance of the biome.

### Key Attributes

| Attribute | Description |
|---|---|
| `name` | Internal identifier for the biome ($biome_town_under). |
| `type` | Specifies the biome generation method (BIOME_WANG_TILE). |
| `background_image` | Path to the main background texture. |
| `background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom` | Paths to textures for background edges, creating seamless transitions. |
| `background_edge_priority` | Determines the rendering order of background edges. |
| `wang_template_file` | Path to the Wang tile image used for generating the biome's structure. |
| `lua_script` | Path to the Lua script that governs biome generation logic. |
| `wang_map_width`, `wang_map_height` | Dimensions of the Wang tile map. |
| `audio_music_2` | Name of the music track to play in this biome. |
| `audio_ambience` | Name of the ambient soundscape for this biome. |

### RandomMaterials

This section allows for dynamic randomization of colors and materials within the biome.

*   `RandomColor`: Defines input colors and a list of possible output colors to substitute, enabling color variations.

### BitmapCaves

Configures the generation of cave structures within the biome.

*   `size_x`, `size_y`: Dimensions of the cave generation grid.
*   `blob_caves_count_min`, `blob_caves_count_max`: Controls the number of blob-like cave formations.
*   `cave_childs_min`, `cave_childs_max`: Defines the range for the number of child caves.
*   `cave_count_min`, `cave_count_max`: Sets the total number of caves to generate.
*   `cave_strength_min`, `cave_strength_max`: Determines the intensity or depth of caves.
*   `mountain_count_min`, `mountain_count_max`: Controls the generation of mountain features.
*   `surface_caves_count_min`, `surface_caves_count_max`: Manages the generation of caves on the surface.
*   `spawn_percent`: Percentage chance for cave generation.

## Materials

The `Materials` element defines the various materials and vegetation present in the biome.

### MaterialComponent

Each `MaterialComponent` defines a specific material and its properties within the biome.

| Attribute | Description |
|---|---|
| `_enabled` | Whether the material component is active (1) or not (0). |
| `is_rare` | Indicates if the material is considered rare (1) or common (0). |
| `limit_max_y`, `limit_min_y`, `limit_y` | Vertical positioning constraints for the material. |
| `material_index` | An internal index for the material. |
| `material_max`, `material_min` | The maximum and minimum density or prevalence of the material. |
| `material_name` | The name of the material (e.g., "coal", "soil", "sand_static", "copper", "gold", "rock_static"). |
| `rare_polka_is_boxed` | Controls how rare material patterns are applied. |
| `rare_polka_probability` | Probability of applying the rare material pattern. |
| `rare_polka_radius_high`, `rare_polka_radius_low` | Defines the radius range for rare material placement. |
| `rare_required_max`, `rare_required_min` | Minimum and maximum requirements for rare material placement. |
| `rare_scale_x`, `rare_scale_y` | Scaling factors for the rare material pattern. |
| `rare_use_perlin` | Whether Perlin noise is used for rare material distribution. |
| `rare_use_polka` | Whether a polka-like pattern is used for rare material distribution. |

**Summary of Materials:**

*   **Coal:** Appears as both common and rare, with varying density and distribution patterns.
*   **Soil:** A common material with specific distribution constraints.
*   **Sand\_static:** Another common material, often found on top of soil.
*   **Copper:** A rare material with specific placement and scaling.
*   **Gold:** A rare material, also with specific placement and scaling.
*   **Rock\_static:** A common, dense material forming the base of the biome.

### VegetationComponent

These components define the vegetation elements within the biome.

| Attribute | Description |
|---|---|
| `_enabled` | Whether the vegetation component is active (1) or not (0). |
| `is_visual` | Indicates if the vegetation is purely visual (1) or has gameplay impact. |
| `rand_seed` | A seed for random generation of this vegetation. |
| `tree_extra_y` | Vertical offset for the vegetation. |
| `tree_image_file` | Path to the XML file defining the vegetation's appearance and properties. |
| `tree_image_visual` | Path to a visual-only image for the vegetation. |
| `tree_material` | The material associated with this vegetation (e.g., "grass", "moss", "ceiling_plant_material", "plant_material"). |
| `tree_probability` | The likelihood of this vegetation appearing. |
| `tree_radius_high`, `tree_radius_low` | Defines the placement radius for the vegetation. |
| `tree_width` | The width of the vegetation sprite. |
| `visual_color` | The color tint applied to the vegetation. |
| `visual_offset_x`, `visual_offset_y` | X and Y offsets for the visual representation. |
| `is_grass` | Specifies if this is a grass element. |
| `grass_requires_neighbors` | If set to 1, grass will only spawn if adjacent to specific materials. |
| `material_on_top_of` | The material this vegetation component can grow on. |
| `is_ceiling_plant` | Indicates if this vegetation grows from the ceiling. |

**Summary of Vegetation:**

*   **Grass:** Common, visual grass with variations in neighbor requirements and the material it grows on.
*   **Moss:** Similar to grass, but specifically grows on `sand_static`.
*   **Ceiling Plants:** Two types of ceiling vegetation are defined, one using a specific XML file (`vine_growth_1.xml`) and another using a pattern of PNG files (`ceiling_vegetation_00$[2-8].png`).
*   **Mushrooms:** A `plant_material` based mushroom growth is also included.