---
title: Fungicave Biome Configuration
category: biome
---

# Fungicave Biome Configuration

This document details the configuration for the Fungicave biome in Noita, focusing on its visual and material properties.

## Topology

The `Topology` element defines the fundamental characteristics of the Fungicave biome, including its visual assets and scripting.

### Key Attributes

| Attribute Name          | Description                                                                 | Example Value                                     |
| :---------------------- | :-------------------------------------------------------------------------- | :------------------------------------------------ |
| `name`                  | Internal identifier for the biome.                                          | `$biome_fungicave`                                |
| `type`                  | Type of biome generation, typically `BIOME_WANG_TILE` for tile-based biomes. | `BIOME_WANG_TILE`                                 |
| `background_image`      | Path to the main background image for the biome.                            | `data/weather_gfx/background_fungicave_01.png`    |
| `background_edge_left`  | Path to the left edge graphic for the background.                           | `data/weather_gfx/edges/background_fungicave_01_left.png` |
| `background_edge_right` | Path to the right edge graphic for the background.                          | `data/weather_gfx/edges/background_fungicave_01_right.png` |
| `background_edge_top`   | Path to the top edge graphic for the background.                            | `data/weather_gfx/edges/background_fungicave_01_top.png` |
| `background_edge_bottom`| Path to the bottom edge graphic for the background.                         | `data/weather_gfx/edges/background_fungicave_01_bottom.png` |
| `wang_template_file`    | Path to the Wang tile template image used for biome generation.             | `data/wang_tiles/fungicave.png`                   |
| `lua_script`            | Path to the Lua script that governs biome-specific behaviors.               | `data/scripts/biomes/fungicave.lua`               |
| `wang_map_width`        | Width of the Wang map grid for this biome.                                  | `260`                                             |
| `wang_map_height`       | Height of the Wang map grid for this biome.                                 | `260`                                             |
| `audio_music_2`         | Name of the music track to play in this biome.                              | `fungicave`                                       |
| `audio_ambience`        | Name of the ambient soundscape for this biome.                              | `fungicave`                                       |

## Materials

The `Materials` section defines the various materials that can spawn within the Fungicave biome and their properties.

### Material Components

Each `MaterialComponent` defines a specific material's spawn conditions and characteristics.

| Attribute Name        | Description                                                                                             | Example Value   |
| :-------------------- | :------------------------------------------------------------------------------------------------------ | :-------------- |
| `name`                | The internal name of the material.                                                                      | `gold`, `fungisoil`, `sand_static`, `rock_static` |
| `material_index`      | Index for the material, often related to its rendering or physics properties.                           | `10`            |
| `material_min`        | Minimum value for this material's density or presence.                                                  | `0.443701`      |
| `material_max`        | Maximum value for this material's density or presence.                                                  | `0.46`          |
| `limit_min_y`         | Minimum Y-coordinate where this material can spawn.                                                     | `100`           |
| `limit_max_y`         | Maximum Y-coordinate where this material can spawn.                                                     | `2048`          |
| `is_rare`             | Whether this material is considered rare (1 for rare, 0 for common).                                    | `1` or `0`      |
| `rare_polka_probability`| Probability of the material appearing in a "polka" pattern (if `rare_use_polka` is 1).                | `0.960871`      |
| `rare_polka_radius_low` | Lower bound of the radius for the polka pattern.                                                        | `0.357143`      |
| `rare_polka_radius_high`| Upper bound of the radius for the polka pattern.                                                        | `0.771429`      |
| `rare_scale_x`        | Scaling factor for the material's texture along the X-axis.                                             | `0.0100004`     |
| `rare_scale_y`        | Scaling factor for the material's texture along the Y-axis.                                             | `0.00357165`    |
| `rare_use_polka`      | Whether to use a polka-like distribution pattern for this material.                                     | `1` or `0`      |

### Vegetation Components

The `VegetationComponent` elements define the decorative elements and flora found within the biome.

| Attribute Name      | Description                                                                                             | Example Value                               |
| :------------------ | :------------------------------------------------------------------------------------------------------ | :------------------------------------------ |
| `is_visual`         | Whether this vegetation is purely visual (1) or can interact with the game world (0).                   | `1` or `0`                                  |
| `tree_image_file`   | Path to the image file(s) for the vegetation. Can use wildcards like `$[1-3]`.                         | `data/vegetation/vine_growth_1.xml`         |
| `tree_material`     | The material associated with this vegetation, affecting its properties.                                 | `ceiling_plant_material`, `fungus_loose`    |
| `tree_probability`  | The likelihood of this vegetation spawning.                                                             | `0.24571`                                   |
| `tree_radius_low`   | Lower bound of the radius for spawning this vegetation.                                                 | `0.146757`                                  |
| `tree_radius_high`  | Upper bound of the radius for spawning this vegetation.                                                 | `0.635286`                                  |
| `tree_width`        | The width of the vegetation sprite.                                                                     | `110.123`                                   |
| `visual_color`      | The color tint applied to the vegetation (RGBA hex format).                                             | `0x00b89f6c`                                |
| `visual_offset_y`   | Vertical offset for the vegetation's visual placement.                                                  | `0` or `7.5`                                |
| `is_ceiling_plant`  | Indicates if the vegetation is intended to grow from the ceiling.                                       | `1`                                         |

```xml
<Biome>
  <Topology 
    name="$biome_fungicave"
    type="BIOME_WANG_TILE"
    background_image="data/weather_gfx/background_fungicave_01.png"
    background_edge_left="data/weather_gfx/edges/background_fungicave_01_left.png"
    background_edge_right="data/weather_gfx/edges/background_fungicave_01_right.png"
    background_edge_top="data/weather_gfx/edges/background_fungicave_01_top.png"
    background_edge_bottom="data/weather_gfx/edges/background_fungicave_01_bottom.png"
    background_edge_priority="9"
    limit_background_image="0"
    wang_template_file="data/wang_tiles/fungicave.png" 
    lua_script="data/scripts/biomes/fungicave.lua"
    wang_map_width="260"
    wang_map_height="260"
    audio_music_2="fungicave"
    audio_ambience="fungicave"
  >
  </Topology>

  <Materials 
    name="fungicave" 
     >
    <MaterialComponent 
      _enabled="1" 
      is_rare="1" 
      limit_max_y="2048" 
      limit_min_y="100" 
      limit_y="0" 
      material_index="10" 
      material_max="0.46" 
      material_min="0.443701" 
      material_name="gold" 
      rare_polka_is_boxed="0" 
      rare_polka_probability="0.960871" 
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
      limit_y="0" 
      material_index="10" 
      material_max="0.66" 
      material_min="0.57" 
      material_name="fungisoil" 
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
      material_min="0.66" 
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
      material_name="gold" 
      rare_polka_is_boxed="1" 
      rare_polka_probability="0.357143" 
      rare_polka_radius_high="0.464286" 
      rare_polka_radius_low="0.0428571" 
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
      is_visual="0" 
      rand_seed="12376.86" 
      tree_extra_y="14" 
      tree_image_file="data/vegetation/mushroom_big_$[1-3].png" 
      tree_image_visual="" 
      tree_material="fungus_loose" 
      tree_probability="0.228571" 
      tree_radius_high="0.414286" 
      tree_radius_low="0.228571" 
      tree_width="76.1143" 
      visual_color="0xffb89f6c" 
      visual_offset_x="3" 
      visual_offset_y="7.5" 
	  >
    </VegetationComponent>
	
	<VegetationComponent 
      _enabled="1" 
      is_visual="0" 
      rand_seed="1245.86" 
      tree_extra_y="14" 
      tree_image_file="data/vegetation/mushroom_big_$[4-6].png" 
      tree_image_visual="" 
      tree_material="fungus_loose" 
      tree_probability="0.128571" 
      tree_radius_high="0.414286" 
      tree_radius_low="0.228571" 
      tree_width="76.1143" 
      visual_color="0xffb89f6c" 
      visual_offset_x="3" 
      visual_offset_y="7.5" 
	  >
    </VegetationComponent>
    
  </Materials>

</Biome>
```