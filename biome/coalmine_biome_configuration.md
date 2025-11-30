---
title: Coalmine Biome Configuration
category: biome
---

# Coalmine Biome Configuration

This document details the configuration for the Coalmine biome in Noita, focusing on key attributes for AI-assisted modding.

## Topology

The `Topology` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes

| Attribute | Description |
|---|---|
| `name` | Internal identifier for the biome (e.g., `$biome_coalmine`). |
| `type` | Type of biome generation, `BIOME_WANG_TILE` indicates Wang tile-based generation. |
| `background_image` | Path to the main background image for the biome. |
| `background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom` | Paths to images used for background edges, creating seamless transitions. |
| `background_edge_priority` | Determines the rendering order of background edges. |
| `wang_template_file` | Path to the Wang tile image used for generating the biome's layout. |
| `lua_script` | Path to the Lua script that controls biome-specific behaviors and generation. |
| `wang_map_width`, `wang_map_height` | Dimensions of the Wang tile map used for generation. |
| `audio_music_2` | Name of the music track associated with this biome. |
| `audio_ambience` | Name of the ambient soundscape for this biome. |

### BitmapCaves

Defines parameters for generating cave structures within the biome.

| Attribute | Description |
|---|---|
| `size_x`, `size_y` | Dimensions of the bitmap used for cave generation. |
| `blob_caves_count_min`, `blob_caves_count_max` | Minimum and maximum number of blob-like cave formations. |
| `cave_childs_min`, `cave_childs_max` | Minimum and maximum number of child caves branching from main caves. |
| `cave_count_min`, `cave_count_max` | Minimum and maximum number of main cave structures. |
| `cave_strength_min`, `cave_strength_max` | Controls the intensity or depth of cave formations. |
| `spawn_percent` | Percentage chance for caves to spawn. |

#### Structures

Defines specific pre-designed cave structures to be placed.

| Attribute | Description |
|---|---|
| `image_file` | Path to the image defining the structure's shape. |
| `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y` | Bounding box coordinates for placing the structure. |
| `count_min`, `count_max` | Minimum and maximum number of times this structure can appear. |
| `strength_min`, `strength_max` | Controls the intensity or depth of the structure. |

## Materials

The `Materials` element defines the various materials that can be found within the biome and their properties.

### MaterialComponent

Each `MaterialComponent` defines a specific material and its generation parameters.

| Attribute | Description |
|---|---|
| `material_name` | The name of the material (e.g., `coal`, `soil`, `sand_static`). |
| `material_index` | An internal index for the material. |
| `material_min`, `material_max` | The minimum and maximum density or prevalence of the material. |
| `limit_min_y`, `limit_max_y` | Vertical limits for where this material can spawn. |
| `is_rare` | If `1`, this material is considered rare. |
| `rare_polka_probability` | Probability of the material appearing in a "polka" pattern. |
| `rare_polka_radius_low`, `rare_polka_radius_high` | Controls the clustering of rare materials. |
| `rare_scale_x`, `rare_scale_y` | Scaling factors for the material's texture or distribution. |
| `rare_use_perlin` | If `1`, Perlin noise is used for distribution. |
| `rare_use_polka` | If `1`, a polka-dot-like distribution is used. |

**Summary of Key Materials:**

*   **Coal:** Appears multiple times with varying rarity and distribution parameters, indicating its prevalence.
*   **Soil:** A common ground material.
*   **Sand\_static:** Another common ground material.
*   **Copper:** A rare material found at higher elevations.
*   **Gold:** A rare material found at higher elevations.
*   **Rock\_static\_wet:** A common, wet rock material.

### VegetationComponent

Defines decorative elements and non-interactive flora within the biome.

| Attribute | Description |
|---|---|
| `is_visual` | If `1`, the vegetation is purely visual. If `0`, it might have gameplay implications (e.g., breakable). |
| `tree_material` | The material name associated with the vegetation (e.g., `grass`, `fungus_loose`, `plant_material`). |
| `tree_probability` | The chance of this vegetation spawning. |
| `tree_radius_low`, `tree_radius_high` | Controls the density and spread of the vegetation. |
| `tree_width` | The visual width of the vegetation sprite. |
| `visual_color` | The color tint applied to the vegetation. |
| `visual_offset_x`, `visual_offset_y` | Offset for the visual sprite. |
| `is_grass` | If `1`, this is a grass-like element. |
| `grass_requires_neighbors` | If `1`, grass will only spawn if adjacent to other grass or specific materials. |
| `material_on_top_of` | Specifies the material this vegetation can grow on. |
| `is_ceiling_plant` | If `1`, this vegetation grows from the ceiling. |
| `tree_image_file` | Path to the image file for the vegetation. Can include wildcards like `$[1-9]`. |

**Summary of Vegetation:**

*   **Grass:** Appears in multiple variations, some requiring neighbors, growing on `soil` and `sand_static`.
*   **Ceiling Plants:** Includes `vine_growth_1.xml` and `aerial_root` variations, growing from the ceiling.
*   **Mushrooms:** Two components for `fungus_loose`, growing on `sand_static`.
*   **Grass Patches:** Larger visual grass patches on `soil` and `sand_static`.

```xml
<Biome>
  <Topology 
    name="$biome_coalmine"
    type="BIOME_WANG_TILE"
    background_image="data/weather_gfx/background_coalmine.png"
    background_edge_left="data/weather_gfx/edges/background_coalmine_left.png"
    background_edge_right="data/weather_gfx/edges/background_coalmine_right.png"
    background_edge_top="data/weather_gfx/edges/background_coalmine_top.png"
    background_edge_bottom="data/weather_gfx/edges/background_coalmine_bottom.png"
    background_edge_priority="10"     
	wang_template_file="data/wang_tiles/coalmine.png" 
    lua_script="data/scripts/biomes/coalmine.lua"
    wang_map_width="256"
    wang_map_height="256"
    audio_music_2="coalmine"
    audio_ambience="cave"
	>
  <RandomMaterials>
    <RandomColor input_color="FF00BBEE" output_colors="FF000000,FFFFFFFF" />
    <RandomColor input_color="FF12BBEE" output_colors="FF000000,FFFFFFFF" />
  </RandomMaterials>
	<BitmapCaves 
      size_x="512"
      size_y="256"
      cave_count_min="2"
      cave_count_max="2"
      cave_strength_min="0.2"
      cave_strength_max="1"
      spawn_percent="0"
      >
      <structures>
        <CaveStructure
          image_file="data/biome_impl/coalmine/dangerroom.png"
          aabb_min_x="5"
          aabb_max_x="507"
          aabb_min_y="0"
          aabb_max_y="230"
          count_min="2"
          count_max="4"
          strength_min="1.45"
          strength_max="1.55" >
        </CaveStructure>
      </structures>
    </BitmapCaves>
  </Topology>

  <Materials name="coalmine">
    <MaterialComponent 
      is_rare="1" 
      limit_min_y="100" 
      material_index="10" 
      material_max="0.55" 
      material_min="0.51" 
      material_name="coal" 
      rare_polka_probability="0.160871" 
      rare_polka_radius_high="0.771429" 
      rare_polka_radius_low="0.357143" 
      rare_scale_x="0.0100004" 
      rare_scale_y="0.00357165" 
      rare_use_polka="1" >
    </MaterialComponent>

    <MaterialComponent 
      is_rare="0" 
      limit_max_y="424.229" 
      limit_min_y="-1024" 
      material_index="10" 
      material_max="0.53" 
      material_min="0.45" 
      material_name="soil" 
      rare_polka_probability="0.2" 
      rare_polka_radius_high="0.65" 
      rare_polka_radius_low="0.2" 
      rare_scale_x="0.05" 
      rare_scale_y="0.05" 
      rare_use_polka="1" >
    </MaterialComponent>

    <MaterialComponent 
      is_rare="0" 
      limit_min_y="100" 
      material_index="10" 
      material_max="0.95" 
      material_min="0.53" 
      material_name="sand_static" 
      rare_polka_probability="0.2" 
      rare_polka_radius_high="0.65" 
      rare_polka_radius_low="0.2" 
      rare_scale_x="0.05" 
      rare_scale_y="0.05" 
      rare_use_polka="1" >
    </MaterialComponent>

    <MaterialComponent 
      is_rare="1" 
      limit_min_y="100" 
      material_index="10" 
      material_max="1.2" 
      material_min="1.1" 
      material_name="coal" 
      rare_polka_probability="0.157143" 
      rare_polka_radius_high="0.464286" 
      rare_polka_radius_low="0.0428571" 
      rare_scale_x="0.0214286" 
      rare_scale_y="0.0214286" 
      rare_use_perlin="1" 
      rare_use_polka="1" >
    </MaterialComponent>

    <MaterialComponent 
      is_rare="1" 
      limit_min_y="750" 
      material_index="10" 
      material_max="1.25" 
      material_min="1.05" 
      material_name="copper" 
      rare_polka_probability="0.357143" 
      rare_polka_radius_high="0.764286" 
      rare_polka_radius_low="0.328571" 
      rare_scale_x="0.007514286" 
      rare_scale_y="0.007514286" 
      rare_use_perlin="1" 
      rare_use_polka="1" >
    </MaterialComponent>
	
	<MaterialComponent 
      is_rare="1" 
      limit_min_y="750" 
      material_index="9" 
      material_max="1.2" 
      material_min="1.05" 
      material_name="gold" 
      rare_polka_probability="0.357143" 
      rare_polka_radius_high="0.564286" 
      rare_polka_radius_low="0.328571" 
      rare_scale_x="0.027514286" 
      rare_scale_y="0.057514286" 
      rare_use_perlin="1" 
      rare_use_polka="1" >
    </MaterialComponent>

    <MaterialComponent 
      is_rare="0" 
      limit_min_y="100" 
      material_index="10" 
      material_max="3.5" 
      material_min="0.9" 
      material_name="rock_static_wet" 
      rare_polka_probability="0.2" 
      rare_polka_radius_high="0.65" 
      rare_polka_radius_low="0.2" 
      rare_scale_x="0.05" 
      rare_scale_y="0.05" 
      rare_use_polka="1" >
    </MaterialComponent>

    <VegetationComponent 
      is_visual="1" 
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
      is_visual="1" 
      tree_material="grass" 
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
      is_visual="1" 
      tree_image_file="data/vegetation/vine_growth_1.xml" 
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
      is_visual="1" 
      tree_image_file="data/vegetation/aerial_root_$[1-9].png" 
      tree_material="ceiling_plant_material" 
      tree_probability="0.54571" 
      tree_radius_high="0.635286" 
      tree_radius_low="0.146757" 
      tree_width="11.123" 
      visual_color="0x00b89f6c" 
      visual_offset_x="3" 
      visual_offset_y="1" 
      is_ceiling_plant="1"
      >
    </VegetationComponent>
	
	<VegetationComponent 
      is_visual="0" 
      tree_image_file="data/vegetation/mushroom_small_0$[1-5].png" 
      tree_material="fungus_loose" 
      tree_probability="0.128571" 
      tree_radius_high="0.414286" 
      tree_radius_low="0.328571" 
      tree_width="18.1143" 
      visual_color="0xffb89f6c" 
      visual_offset_x="3" 
      visual_offset_y="1"
	  material_on_top_of="sand_static"
	  >
    </VegetationComponent>
	
	<VegetationComponent 
      is_visual="0" 
      tree_image_file="data/vegetation/mushroom_small_0$[6-9].png" 
      tree_material="fungus_loose" 
      tree_probability="0.128571" 
      tree_radius_high="0.414286" 
      tree_radius_low="0.328571" 
      tree_width="16.1143" 
      visual_color="0xffb89f6c" 
      visual_offset_x="3" 
      visual_offset_y="1"
	  material_on_top_of="sand_static"
	  >
    </VegetationComponent>
	
	<VegetationComponent 
      is_visual="1" 
      tree_image_file="data/vegetation/grass_patch_0$[3-6].xml" 
      tree_material="plant_material" 
      tree_probability="0.328571" 
      tree_radius_high="0.154286" 
      tree_radius_low="0.1027" 
      tree_width="20" 
      visual_color="0xff4d5d44" 
      visual_offset_x="15" 
      visual_offset_y="32"
	  material_on_top_of="soil"
	  >
    </VegetationComponent>
	
	<VegetationComponent 
      is_visual="1" 
      tree_image_file="data/vegetation/grass_patch_0$[3-6].xml" 
      tree_material="plant_material" 
      tree_probability="0.468571" 
      tree_radius_high="0.154286" 
      tree_radius_low="0.1027" 
      tree_width="20" 
      visual_color="0xff4d5d44" 
      visual_offset_x="15" 
      visual_offset_y="32"
	  material_on_top_of="sand_static"
	  >
    </VegetationComponent>
  </Materials>
</Biome>
```