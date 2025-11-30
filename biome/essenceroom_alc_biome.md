---
title: Essenceroom Alc Biome
category: biome
---

# Essenceroom Alc Biome

This document details the configuration for the "Essenceroom Alc" biome in Noita, focusing on its generation parameters and material distribution.

## Topology

The `Topology` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `type`                    | Specifies the biome generation type, here `BIOME_WANG_TILE`.                |
| `background_image`        | Path to the main background image for the biome.                            |
| `background_edge_left`    | Path to the left edge background image.                                     |
| `background_edge_right`   | Path to the right edge background image.                                    |
| `background_edge_top`     | Path to the top edge background image.                                      |
| `background_edge_bottom`  | Path to the bottom edge background image.                                   |
| `background_edge_priority`| Determines the layering priority of background edges.                       |
| `wang_template_file`      | Path to the Wang tile template file (empty in this case).                   |
| `lua_script`              | Path to the Lua script that governs biome-specific logic.                   |
| `wang_map_width`          | Width of the Wang map used for generation.                                  |
| `wang_map_height`         | Height of the Wang map used for generation.                                 |
| `audio_music_2`           | Name of the music track to play in this biome.                              |
| `audio_ambience`          | Name of the ambient soundscape for the biome.                               |

### BitmapCaves

This section controls the procedural generation of cave structures within the biome.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `size_x`                  | Width of the cave generation grid.                                          |
| `size_y`                  | Height of the cave generation grid.                                         |
| `spawn_percent`           | Percentage of the grid to be filled with caves.                             |
| `blob_caves_count_min`    | Minimum number of blob caves to generate.                                   |
| `blob_caves_count_max`    | Maximum number of blob caves to generate.                                   |
| `blob_caves_radius_min`   | Minimum radius for blob caves.                                              |
| `blob_caves_radius_max`   | Maximum radius for blob caves.                                              |
| `blob_caves_strength_min` | Minimum strength (density/impact) of blob caves.                            |
| `blob_caves_strength_max` | Maximum strength (density/impact) of blob caves.                            |
| `cave_childs_min`         | Minimum number of child caves branching from main caves.                    |
| `cave_childs_max`         | Maximum number of child caves branching from main caves.                    |
| `cave_count_min`          | Minimum number of main caves.                                               |
| `cave_count_max`          | Maximum number of main caves.                                               |
| `cave_strength_min`       | Minimum strength of main caves.                                             |
| `cave_strength_max`       | Maximum strength of main caves.                                             |
| `mountain_count_min`      | Minimum number of mountain-like structures.                                 |
| `mountain_count_max`      | Maximum number of mountain-like structures.                                 |
| `surface_caves_count_min` | Minimum number of surface caves.                                            |
| `surface_caves_count_max` | Maximum number of surface caves.                                            |

## Materials

The `Materials` element defines the distribution and properties of different materials within the biome.

### Material Components

Each `MaterialComponent` defines a specific material and its generation parameters.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `material_name`           | The name of the material (e.g., "sand_static", "diamond").                  |
| `material_index`          | An internal index for the material.                                         |
| `material_min`            | Minimum density/probability of the material.                                |
| `material_max`            | Maximum density/probability of the material.                                |
| `limit_min_y`             | Minimum Y-coordinate where this material can spawn.                         |
| `limit_max_y`             | Maximum Y-coordinate where this material can spawn.                         |
| `limit_y`                 | A specific Y-level constraint for the material.                             |
| `is_rare`                 | Indicates if the material is considered rare (1 for rare, 0 for common).    |
| `rare_polka_probability`  | Probability of the material appearing in a "polka" pattern.                 |
| `rare_polka_radius_low`   | Minimum radius for the polka pattern.                                       |
| `rare_polka_radius_high`  | Maximum radius for the polka pattern.                                       |
| `rare_scale_x`            | Scaling factor for the material's texture on the X-axis.                    |
| `rare_scale_y`            | Scaling factor for the material's texture on the Y-axis.                    |
| `add_perlin`              | Whether to add Perlin noise for texture variation (1 for yes, 0 for no).    |
| `add_perlin_scale_y`      | Scaling factor for Perlin noise on the Y-axis.                              |
| `add_perlin_scale_x`      | Scaling factor for Perlin noise on the X-axis.                              |

#### Example Material Components:

*   **`sand_static`**: A common material with a moderate density range and specific Y-level limits.
*   **`diamond`**: A rare material with a higher probability of appearing in a polka pattern and smaller texture scaling.
*   **`rock_hard`**: A common material with Perlin noise applied for texture variation.
*   **`templebrickdark_static`**: Another common material with Perlin noise for texture.

```xml
<Biome>
  <Topology 
    name="???"
    type="BIOME_WANG_TILE"
	background_use_neighbor="0"
    background_image="data/weather_gfx/background_crypt.png"
    background_edge_left="data/weather_gfx/edges/background_crypt_left.png"
    background_edge_right="data/weather_gfx/edges/background_crypt_right.png"
    background_edge_top="data/weather_gfx/edges/background_crypt_top.png"
    background_edge_bottom="data/weather_gfx/edges/background_crypt_bottom.png"
    background_edge_priority="12"     
    wang_template_file="" 
    lua_script="data/scripts/biomes/essenceroom_alc.lua"
    wang_map_width="256"
    wang_map_height="256"
    audio_music_2="wandcave"
    audio_ambience="cave"
  >
  <BitmapCaves 
      size_x="256"
      size_y="256"
      spawn_percent="0"
      blob_caves_count_min="0"
      blob_caves_count_max="1"
      blob_caves_radius_min="1"
      blob_caves_radius_max="1"
      blob_caves_strength_min="1.2"
      blob_caves_strength_max="2"
      cave_childs_min="0"
      cave_childs_max="1"
      cave_count_min="1"
      cave_count_max="2"
      cave_strength_min="0.2"
      cave_strength_max="1.8"
      mountain_count_min="0"
      mountain_count_max="0"
      mountain_size_min="1"
      mountain_size_max="10"
      surface_cave_childs_min="0"
      surface_cave_childs_max="0"
      surface_caves_count_min="0" 
      surface_caves_count_max="0"
	  >
    </BitmapCaves>
  </Topology>

  <Materials 
    name="???" 
     >
    <MaterialComponent 
      _enabled="1" 
      is_rare="0" 
      limit_max_y="424.229" 
      limit_min_y="-1024" 
      limit_y="1" 
      material_index="10" 
      material_max="0.55" 
      material_min="0.45" 
      material_name="sand_static" 
      rare_polka_is_boxed="1" 
      rare_polka_probability="0.2" 
      rare_polka_radius_high="0.65" 
      rare_polka_radius_low="0.2" 
      rare_required_max="10" 
      rare_required_min="0.2" 
      rare_scale_x="0.05" 
      rare_scale_y="0.05" 
      rare_use_perlin="0" 
      rare_use_polka="1" >
    </MaterialComponent>

    <MaterialComponent 
      _enabled="1" 
      is_rare="1" 
      limit_max_y="2048" 
      limit_min_y="100" 
      limit_y="0" 
      material_index="10" 
      material_max="1.2" 
      material_min="1.1" 
      material_name="diamond" 
      rare_polka_is_boxed="1" 
      rare_polka_probability="0.757143" 
      rare_polka_radius_high="0.464286" 
      rare_polka_radius_low="0.1428571" 
      rare_required_max="10" 
      rare_required_min="0.371429" 
      rare_scale_x="0.0214286" 
      rare_scale_y="0.0214286" 
      rare_use_perlin="0" 
      rare_use_polka="1" >
    </MaterialComponent>
    
    <MaterialComponent 
      _enabled="1" 
      is_rare="0" 
      limit_max_y="2048" 
      limit_min_y="100" 
      limit_y="0" 
      material_index="10" 
      material_max="1.0" 
      material_min="0.6" 
      material_name="rock_hard" 
      add_perlin="1"
      add_perlin_scale_y="0.01"
      add_perlin_scale_x="0.01"
      rare_polka_is_boxed="1" 
      rare_polka_probability="0.2" 
      rare_polka_radius_high="0.65" 
      rare_polka_radius_low="0.2" 
      rare_required_max="10" 
      rare_required_min="0.2" 
      rare_scale_x="0.05" 
      rare_scale_y="0.05" 
      rare_use_perlin="0" 
      rare_use_polka="1" >
    </MaterialComponent>
	
	<MaterialComponent 
      _enabled="1" 
      is_rare="0" 
      limit_max_y="2048" 
      limit_min_y="100" 
      limit_y="0" 
      material_index="11" 
      material_max="3.6" 
      material_min="0.8" 
      material_name="templebrickdark_static" 
      add_perlin="1"
      add_perlin_scale_y="0.01"
      add_perlin_scale_x="0.01"
      rare_polka_is_boxed="1" 
      rare_polka_probability="0.2" 
      rare_polka_radius_high="0.65" 
      rare_polka_radius_low="0.2" 
      rare_required_max="10" 
      rare_required_min="0.2" 
      rare_scale_x="0.05" 
      rare_scale_y="0.05" 
      rare_use_perlin="0" 
      rare_use_polka="1" >
    </MaterialComponent>
    
  </Materials>

</Biome>
```