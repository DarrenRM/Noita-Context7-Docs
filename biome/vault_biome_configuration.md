---
title: Vault Biome Configuration
category: biome
---

---

# Vault Biome Configuration

This document details the configuration for the Vault biome in Noita, focusing on its visual and material properties.

## Topology

The `<Topology>` element defines the fundamental characteristics of the Vault biome, including its visual assets and generation parameters.

### Key Attributes

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `name`                    | Internal identifier for the biome (`$biome_vault`).                         |
| `type`                    | Biome type, set to `BIOME_WANG_TILE`.                                       |
| `background_image`        | Path to the main background image for the biome.                            |
| `background_edge_left`    | Path to the left edge background image.                                     |
| `background_edge_right`   | Path to the right edge background image.                                    |
| `background_edge_top`     | Path to the top edge background image.                                      |
| `background_edge_bottom`  | Path to the bottom edge background image.                                   |
| `background_edge_priority`| Determines the rendering order of background edges.                         |
| `wang_template_file`      | Path to the Wang tile template image used for biome generation.             |
| `lua_script`              | Path to the Lua script responsible for biome-specific logic.                |
| `wang_map_width`          | Width of the Wang map used for generation.                                  |
| `wang_map_height`         | Height of the Wang map used for generation.                                 |
| `audio_music_2`           | Name of the music track to play in this biome.                              |
| `audio_ambience`          | Name of the ambient soundscape for this biome.                              |

### BitmapCaves

This nested element controls the generation of cave structures within the biome.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `size_x`                   | Width of the cave generation area.                                          |
| `size_y`                  | Height of the cave generation area.                                         |
| `spawn_percent`           | Percentage of the area to spawn caves (0 means none by default).            |
| `blob_caves_count_min`    | Minimum number of blob caves to generate.                                   |
| `blob_caves_radius_max`   | Maximum radius of blob caves.                                               |
| `cave_count_min`          | Minimum number of general caves to generate.                                |
| `cave_strength_max`       | Maximum strength/density of generated caves.                                |
| `mountain_count_max`      | Maximum number of mountains to generate (set to 0 for Vault).               |

## Materials

The `<Materials>` element defines the different materials that can appear within the Vault biome and their distribution.

### MaterialComponent

Each `<MaterialComponent>` defines a specific material and its properties.

| Attribute             | Description                                                                                             |
| :-------------------- | :------------------------------------------------------------------------------------------------------ |
| `material_name`       | The name of the material (e.g., `gold`, `soil`, `rock_vault`).                                          |
| `material_index`      | An index for the material, often related to its rendering or processing.                                |
| `material_min`        | Minimum value for this material's density/presence.                                                     |
| `material_max`        | Maximum value for this material's density/presence.                                                     |
| `is_rare`             | Whether this material is considered rare (`1` for rare, `0` for common).                                |
| `limit_min_y`         | Minimum Y-coordinate where this material can spawn.                                                     |
| `limit_max_y`         | Maximum Y-coordinate where this material can spawn.                                                     |
| `rare_use_polka`      | Whether to use a polka distribution pattern for rare materials.                                         |
| `rare_polka_probability`| Probability of a rare material appearing when polka distribution is used.                               |
| `rare_scale_x`        | Scaling factor for the rare material's texture along the X-axis.                                        |
| `rare_scale_y`        | Scaling factor for the rare material's texture along the Y-axis.                                        |

#### Example Material Components:

*   **Gold:** A rare material with specific Y-limits and a high polka probability.
*   **Soil:** A common material with broader Y-limits.
*   **Rock Vault:** A common rock type specific to the Vault biome.
*   **Radioactive Liquid:** A rare liquid material with unique scaling and probability settings.
*   **Rock Static:** A common static rock material.

### VegetationComponent

These components define the vegetation that can spawn in the biome.

| Attribute             | Description                                                                                             |
| :-------------------- | :------------------------------------------------------------------------------------------------------ |
| `is_visual`           | Whether this vegetation is purely visual (`1`) or has gameplay impact.                                  |
| `tree_image_file`     | Path to the image file for the vegetation. Can use wildcards like `$[2-8]`.                             |
| `tree_material`       | The material associated with this vegetation (e.g., `snow`, `ceiling_plant_material`).                  |
| `tree_probability`    | The chance of this vegetation spawning.                                                                 |
| `tree_radius_high`    | Maximum radius for placement.                                                                           |
| `tree_radius_low`     | Minimum radius for placement.                                                                           |
| `visual_color`        | The color tint for the visual representation of the vegetation.                                         |
| `is_grass`            | If `1`, this component represents grass.                                                                |
| `grass_requires_neighbors`| If `1`, grass will only spawn if adjacent to specific materials.                                      |
| `material_on_top_of`  | Specifies the material the grass must be on top of.                                                     |
| `is_ceiling_plant`    | If `1`, this component represents a plant growing from the ceiling.                                     |

#### Example Vegetation Components:

*   **Snow Grass:** A visual grass component with a specific material and placement constraints.
*   **Vine Growth:** A ceiling plant with a defined image file and probability.
*   **Hanger Vegetation:** Another type of ceiling plant with a different image file pattern.