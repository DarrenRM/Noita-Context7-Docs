---
title: Mountain Hall 4 Biome Configuration
category: biome
---

# Mountain Hall 4 Biome Configuration

This document details the configuration for the "Mountain Hall 4" biome in Noita, focusing on its environmental properties and material distribution.

## Topology

The `Topology` element defines the fundamental structure and appearance of the biome.

### Key Attributes

| Attribute             | Value                                    | Description                                                                 |
| :-------------------- | :--------------------------------------- | :-------------------------------------------------------------------------- |
| `name`                | `_EMPTY_`                                | Internal identifier for this topology.                                      |
| `type`                | `BIOME_WANG_TILE`                        | Indicates this biome uses Wang tiles for generation.                        |
| `background_image`    | `data/weather_gfx/background_cave_02.png` | The background image used for this biome.                                   |
| `background_use_neighbor` | `0`                                      | Whether to use neighbor information for background blending.                |
| `wang_template_file`  | `""`                                     | Path to the Wang template file (empty here, likely uses default logic).     |
| `lua_script`          | `data/scripts/biomes/mountain/mountain_hall_4.lua` | The Lua script that governs biome generation and behavior.                  |
| `wang_map_width`      | `256`                                    | The width of the generated Wang map.                                        |
| `wang_map_height`     | `256`                                    | The height of the generated Wang map.                                       |
| `coarse_map_force_terrain` | `1`                                      | Forces terrain generation on the coarse map.                                |
| `audio_ambience`      | `cave`                                   | The ambient soundscape for this biome.                                      |
| `skip_edge_textures`  | `1`                                      | Skips applying textures to the edges of the biome.                          |

## Materials

The `Materials` element defines the types of materials present in the biome and their distribution.

### Key Material Components

This section lists the primary `MaterialComponent` and `VegetationComponent` entries, highlighting their key properties.

#### Material Components

| Material Name | `is_rare` | `limit_min_y` | `limit_max_y` | `material_min` | `material_max` | `rare_use_polka` | `rare_use_perlin` |
| :------------ | :-------- | :------------ | :------------ | :------------- | :------------- | :--------------- | :---------------- |
| `coal`        | `1`       | `100`         | `2048`        | `0.51`         | `0.55`         | `1`              | `0`               |
| `soil`        | `0`       | `-1024`       | `424.229`     | `0.45`         | `0.53`         | `1`              | `0`               |
| `rock_hard`   | `0`       | `100`         | `2048`        | `0.53`         | `0.95`         | `1`              | `0`               |
| `coal`        | `1`       | `100`         | `2048`        | `1.1`          | `1.2`          | `1`              | `1`               |
| `copper`      | `1`       | `750`         | `2048`        | `1.05`         | `1.25`         | `1`              | `1`               |
| `gold`        | `1`       | `750`         | `2048`        | `1.05`         | `1.2`          | `1`              | `1`               |
| `rock_static` | `0`       | `100`         | `2048`        | `0.9`          | `3.5`          | `1`              | `0`               |

**Summary of Material Distribution:**

*   **Coal:** Appears in two forms, one common and one rare, with varying density and distribution ranges. The rare variant uses Perlin noise.
*   **Soil:** Primarily found in lower sections of the biome.
*   **Rock (Hard & Static):** Forms the bulk of the terrain, with `rock_hard` having a moderate density and `rock_static` being more abundant.
*   **Copper & Gold:** Rare materials found at higher elevations (`limit_min_y="750"`), suggesting they are more likely to be encountered deeper within the mountain. Both use Perlin noise and polka for distribution.

#### Vegetation Components

| Component Type      | `is_visual` | `tree_material`      | `tree_probability` | `is_grass` | `is_ceiling_plant` | `material_on_top_of` |
| :------------------ | :---------- | :------------------- | :----------------- | :--------- | :----------------- | :------------------- |
| `VegetationComponent` | `1`         | `grass`              | `0.828571`         | `1`        | `0`                | `soil`               |
| `VegetationComponent` | `1`         | `moss`               | `0.828571`         | `1`        | `0`                | `sand_static`        |
| `VegetationComponent` | `1`         | `ceiling_plant_material` | `0.24571`          | `0`        | `1`                | N/A                  |
| `VegetationComponent` | `1`         | `ceiling_plant_material` | `0.54571`          | `0`        | `1`                | N/A                  |
| `VegetationComponent` | `1`         | `plant_material`     | `0.828571`         | `0`        | `0`                | N/A                  |

**Summary of Vegetation:**

*   **Grass & Moss:** Abundant ground cover, with grass preferring soil and moss preferring sand.
*   **Ceiling Plants:** Two types of ceiling vegetation are present, with one being more common.
*   **Mushrooms:** A specific mushroom growth variant is also included.

```xml
<Biome>
  <Topology 
    name="_EMPTY_"
	  type="BIOME_WANG_TILE"
    background_image="data/weather_gfx/background_cave_02.png"
    background_use_neighbor="0"
    wang_template_file="" 
    lua_script="data/scripts/biomes/mountain/mountain_hall_4.lua"
    wang_map_width="256"
    wang_map_height="256"
	  limit_background_image="0"
    coarse_map_force_terrain="1"
    audio_ambience="cave"
    skip_edge_textures="1"
    >
  </Topology>

  <Materials 
    name="mountain" 
     >
    <MaterialComponent 
      _enabled="1" 
      is_rare="1" 
      limit_max_y="2048" 
      limit_min_y="100" 
      limit_y="0" 
      material_index="10" 
      material_max="0.55" 
      material_min="0.51" 
      material_name="coal" 
      rare_polka_is_boxed="0" 
      rare_polka_probability="0.160871" 
      rare_polka_radius_high="0.771429" 
      rare_polka_radius_low="0.357143" 
      rare_required_max="10" 
      rare_required_min="0" 
      rare_scale_x="0.0100004" 
      rare_scale_y="0.00357165" 
      rare_use_perlin="0" 
      rare_use_polka="1" >
    </MaterialComponent>

    <MaterialComponent 
      _enabled="1" 
      is_rare="0" 
      limit_max_y="424.229" 
      limit_min_y="-1024" 
      limit_y="1" 
      material_index="10" 
      material_max="0.53" 
      material_min="0.45" 
      material_name="soil" 
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
      material_index="10" 
      material_max="0.95" 
      material_min="0.53" 
      material_name="rock_hard" 
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
      material_name="coal" 
      rare_polka_is_boxed="1" 
      rare_polka_probability="0.157143" 
      rare_polka_radius_high="0.464286" 
      rare_polka_radius_low="0.0428571" 
      rare_required_max="10" 
      rare_required_min="0.371429" 
      rare_scale_x="0.0214286" 
      rare_scale_y="0.0214286" 
      rare_use_perlin="1" 
      rare_use_polka="1" >
    </MaterialComponent>

    <MaterialComponent 
      _enabled="1" 
      is_rare="1" 
      limit_max_y="2048" 
      limit_min_y="750" 
      limit_y="1" 
      material_index="10" 
      material_max="1.25" 
      material_min="1.05" 
      material_name="copper" 
      rare_polka_is_boxed="0" 
      rare_polka_probability="0.357143" 
      rare_polka_radius_high="0.764286" 
      rare_polka_radius_low="0.328571" 
      rare_required_max="10" 
      rare_required_min="0.019" 
      rare_scale_x="0.007514286" 
      rare_scale_y="0.007514286" 
      rare_use_perlin="1" 
      rare_use_polka="1" >
    </MaterialComponent>
	
	<MaterialComponent 
      _enabled="1" 
      is_rare="1" 
      limit_max_y="2048" 
      limit_min_y="750" 
      limit_y="0" 
      material_index="9" 
      material_max="1.2" 
      material_min="1.05" 
      material_name="gold" 
      rare_polka_is_boxed="0" 
      rare_polka_probability="0.357143" 
      rare_polka_radius_high="0.564286" 
      rare_polka_radius_low="0.328571" 
      rare_required_max="10" 
      rare_required_min="0.019" 
      rare_scale_x="0.027514286" 
      rare_scale_y="0.057514286" 
      rare_use_perlin="1" 
      rare_use_polka="1" >
    </MaterialComponent>

    <MaterialComponent 
      _enabled="1" 
      is_rare="0" 
      limit_max_y="2048" 
      limit_min_y="100" 
      limit_y="0" 
      material_index="10" 
      material_max="3.5" 
      material_min="0.9" 
      material_name="rock_static" 
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

    <VegetationComponent 
      _enabled="1" 
      is_visual="1" 
      rand_seed="8376.86" 
      tree_extra_y="0" 
      tree_image_file="" 
      tree_image_visual="" 
      tree_material="grass" 
      tree_probability="0.828571" 
      tree_radius_high="0.414286" 
      tree_radius_low="0.228571" 
      tree_width="76.1143" 
      visual_color="0xffb89f6c" 
      visual_offset_x="3" 
      visual_offset_y="7.5" 
      is_grass="1"
      grass_requires_neighbors="0"
      material_on_top_of="soil"
      >
    </VegetationComponent>

    <VegetationComponent 
      _enabled="1" 
      is_visual="1" 
      rand_seed="8376.86" 
      tree_extra_y="0" 
      tree_image_file="" 
      tree_image_visual="" 
      tree_material="moss" 
      tree_probability="0.828571" 
      tree_radius_high="0.414286" 
      tree_radius_low="0.228571" 
      tree_width="76.1143" 
      visual_color="0xffb89f6c" 
      visual_offset_x="3" 
      visual_offset_y="7.5" 
      is_grass="1"
      grass_requires_neighbors="1"
      material_on_top_of="sand_static"
      >
    </VegetationComponent>

    <VegetationComponent 
      _enabled="1" 
      is_visual="1" 
      rand_seed="1248" 
      tree_extra_y="0" 
      tree_image_file="data/vegetation/vine_growth_1.xml" 
      tree_image_visual="" 
      tree_material="ceiling_plant_material" 
      tree_probability="0.24571" 
      tree_radius_high="0.635286" 
      tree_radius_low="0.146757" 
      tree_width="110.123" 
      visual_color="0x00b89f6c" 
      visual_offset_x="3" 
      visual_offset_y="0" 
      is_ceiling_plant="1"
      >
    </VegetationComponent>
    <VegetationComponent 
      _enabled="1" 
      is_visual="1" 
      rand_seed="4575" 
      tree_extra_y="0" 
      tree_image_file="data/vegetation/ceiling_vegetation_00$[2-8].png" 
      tree_image_visual="" 
      tree_material="ceiling_plant_material" 
      tree_probability="0.54571" 
      tree_radius_high="0.635286" 
      tree_radius_low="0.146757" 
      tree_width="11.123" 
      visual_color="0x00b89f6c" 
      visual_offset_x="3" 
      visual_offset_y="0" 
      is_ceiling_plant="1"
      >
    </VegetationComponent>

       <VegetationComponent 
      _enabled="1" 
      is_visual="1" 
      rand_seed="8376.86" 
      tree_extra_y="0" 
      tree_image_file="data/vegetation/mushroom_growth_2.xml" 
      tree_image_visual="" 
      tree_material="plant_material" 
      tree_probability="0.828571" 
      tree_radius_high="0.414286" 
      tree_radius_low="0.228571" 
      tree_width="76.1143" 
      visual_color="0xffb89f6c" 
      visual_offset_x="3" 
      visual_offset_y="7.5" >
    </VegetationComponent>
    
  </Materials>

</Biome>
```