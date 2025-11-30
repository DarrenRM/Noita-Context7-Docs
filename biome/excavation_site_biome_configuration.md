---
title: Excavation Site Biome Configuration
category: biome/
---

# Excavation Site Biome Configuration

This document details the configuration for the Excavation Site biome in Noita, focusing on its generation, material composition, and visual elements.

## Topology

The `Topology` element defines the fundamental generation parameters for the Excavation Site.

### Key Attributes

| Attribute | Description |
|---|---|
| `name` | Internal identifier for the biome (e.g., `$biome_excavationsite`). |
| `type` | Biome generation method, `BIOME_WANG_TILE` indicates it uses Wang tiles for generation. |
| `background_image` | Path to the main background image for the biome. |
| `background_edge_*` | Paths to images used for background edges (left, right, top, bottom). |
| `background_edge_priority` | Determines the rendering order of background edges. |
| `wang_template_file` | Path to the Wang tile image used for generating the biome's structure. |
| `lua_script` | Path to the Lua script that controls biome-specific behaviors and generation. |
| `wang_map_width`, `wang_map_height` | Dimensions of the Wang tile map used for generation. |
| `audio_music_2` | Name of the music track to play in this biome. |
| `audio_ambience` | Name of the ambient soundscape for this biome. |

### BitmapCaves

This section configures the generation of cave structures within the biome.

| Attribute | Description |
|---|---|
| `size_x`, `size_y` | Dimensions of the cave generation area. |
| `blob_caves_count_min`, `blob_caves_count_max` | Minimum and maximum number of blob-like cave formations. |
| `cave_childs_min`, `cave_childs_max` | Controls the branching of caves. |
| `cave_count_min`, `cave_count_max` | Minimum and maximum number of main cave structures. |
| `cave_strength_min`, `cave_strength_max` | Controls the density and prominence of cave walls. |
| `mountain_count_min`, `mountain_count_max` | Minimum and maximum number of mountain-like formations (set to 0 here). |
| `surface_caves_count_min`, `surface_caves_count_max` | Controls surface cave generation (set to 0 here). |
| `spawn_percent` | Percentage of the biome area where caves can spawn. |

#### Structures

| Element | Description |
|---|---|
| `CaveStructure` | Defines specific pre-designed cave structures to be placed. |
| `image_file` | Path to the image defining the structure's shape. |
| `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y` | Bounding box for structure placement. |
| `count_min`, `count_max` | Minimum and maximum number of times this structure can appear. |
| `strength_min`, `strength_max` | Controls the intensity or prominence of the structure. |

## Materials

The `Materials` element defines the various materials that can be found within the Excavation Site biome and their properties.

### MaterialComponent

Each `MaterialComponent` defines a specific material and its generation parameters.

| Attribute | Description |
|---|---|
| `_enabled` | Whether this component is active (1) or not (0). |
| `is_rare` | Indicates if the material is rare (1) or common (0). |
| `limit_max_y`, `limit_min_y`, `limit_y` | Vertical limits for material placement. |
| `material_index` | Internal index for the material. |
| `material_max`, `material_min` | Controls the density or quantity of the material. |
| `material_name` | The name of the material (e.g., `coal`, `diamond`, `rock_static_grey`). |
| `rare_polka_is_boxed`, `rare_polka_probability`, `rare_polka_radius_high`, `rare_polka_radius_low` | Parameters for "polka dot" distribution of rare materials. |
| `rare_required_max`, `rare_required_min` | Minimum and maximum required density for rare material placement. |
| `rare_scale_x`, `rare_scale_y` | Scaling factors for rare material distribution. |
| `rare_use_perlin`, `rare_use_polka` | Flags to enable Perlin noise or polka dot distribution for rare materials. |
| `add_perlin`, `add_perlin_scale_y`, `add_perlin_scale_x` | Parameters for adding Perlin noise to material distribution. |

#### Key Materials and Their Properties

*   **Coal:** Appears as both common and rare variants. Rare coal uses polka dot distribution and Perlin noise.
*   **Diamond:** Appears as a common material and a rarer variant found at higher Y-levels.
*   **Rock\_static\_grey:** A common static rock material.
*   **Gold:** A rare material found at higher Y-levels, with polka dot distribution.
*   **Coal\_static:** A static coal variant with Perlin noise added.

### VegetationComponent

These components define the visual elements like grass, plants, and mushrooms that appear in the biome.

| Attribute | Description |
|---|---|
| `_enabled` | Whether this vegetation component is active (1) or not (0). |
| `is_visual` | If 1, it's purely visual; if 0, it can have gameplay effects (e.g., harvestable). |
| `rand_seed` | Seed for random generation of this vegetation. |
| `tree_extra_y` | Vertical offset for the vegetation. |
| `tree_image_file` | Path to the image file for the vegetation. Can use wildcards like `$[1-5]`. |
| `tree_image_visual` | Path to a separate visual image (often empty). |
| `tree_material` | The material associated with this vegetation (e.g., `grass`, `moss`, `snow`, `fungus_loose`). |
| `tree_probability` | Likelihood of this vegetation appearing. |
| `tree_radius_high`, `tree_radius_low` | Controls the distribution radius. |
| `tree_width` | Width of the vegetation sprite. |
| `visual_color` | Color tint for the vegetation (RGBA hex format). |
| `visual_offset_x`, `visual_offset_y` | Offset for the visual sprite. |
| `is_grass` | If 1, this is a grass-like element. |
| `grass_requires_neighbors` | If 1, grass only spawns if adjacent tiles meet certain criteria. |
| `material_on_top_of` | Specifies the material this vegetation can grow on. |
| `is_ceiling_plant` | If 1, this vegetation grows from the ceiling. |

#### Key Vegetation Types

*   **Grass and Moss:** Common ground cover, with variations in placement rules.
*   **Snow:** Initially has 0 probability, likely intended for biome modifiers.
*   **Ceiling Plants:** Vines and other flora that grow from the ceiling.
*   **Mushrooms:** Non-visual (harvestable) mushrooms with different sprite sets.
*   **Red Plant:** A distinct visual plant with specific color and placement.

```xml
<Biome>
  <Topology 
    name="$biome_excavationsite"
    type="BIOME_WANG_TILE"
    background_image="data/weather_gfx/background_excavationsite.png"
    background_edge_left="data/weather_gfx/edges/background_excavationsite_left.png"
    background_edge_right="data/weather_gfx/edges/background_excavationsite_right.png"
    background_edge_top="data/weather_gfx/edges/background_excavationsite_top.png"
    background_edge_bottom="data/weather_gfx/edges/background_excavationsite_bottom.png"
    background_edge_priority="10"     
    limit_background_image="0"
    noise_biome_edges="1"
    wang_template_file="data/wang_tiles/excavationsite.png" 
    lua_script="data/scripts/biomes/excavationsite.lua"
    wang_map_width="256"
    wang_map_height="256"
    audio_music_2="excavationsite"
    audio_ambience="excavationsite">
	<BitmapCaves 
      size_x="512"
      size_y="256"
      blob_caves_count_min="0"
      blob_caves_count_max="0"
      cave_childs_min="0"
      cave_childs_max="1"
      cave_count_min="2"
      cave_count_max="2"
      cave_strength_min="0.2"
      cave_strength_max="1"
      mountain_count_min="0"
      mountain_count_max="0"
      surface_caves_count_min="0" 
      surface_caves_count_max="0" 
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

  <Materials 
    name="excavationsite" 
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
      material_name="diamond" 
	  >
    </MaterialComponent>

    <MaterialComponent 
      _enabled="1" 
      is_rare="0" 
      limit_max_y="2048" 
      limit_min_y="100" 
      limit_y="0" 
      material_index="10" 
      material_max="1.55" 
      material_min="0.53" 
      material_name="rock_static_grey" 
	  >
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
      material_name="diamond" 
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
      rare_polka_radius_high="0.664286" 
      rare_polka_radius_low="0.428571" 
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
      material_index="9" 
      material_max="3.5" 
      material_min="0.8" 
      material_name="coal_static"
	  add_perlin="1"
      add_perlin_scale_y="0.02"
      add_perlin_scale_x="0.01"
	  >
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
      material_on_top_of="rock_static_grey"
      >
    </VegetationComponent>

    <!-- this is for the FREEZING biome modifier. tree_probability should initially be 0 -->
    <VegetationComponent 
      _enabled="1" 
      is_visual="1" 
      rand_seed="8376.86" 
      tree_extra_y="0" 
      tree_image_file="" 
      tree_image_visual="" 
      tree_material="snow" 
      tree_probability="0" 
      tree_radius_high="0.414286" 
      tree_radius_low="0.228571" 
      tree_width="76.1143" 
      visual_color="0xffb89f6c" 
      visual_offset_x="3" 
      visual_offset_y="7.5" 
      is_grass="1"
      grass_requires_neighbors="1"
      material_on_top_of="coal_static"
    ></VegetationComponent>
    <VegetationComponent 
      _enabled="1" 
      is_visual="1" 
      rand_seed="8376.86" 
      tree_extra_y="0" 
      tree_image_file="" 
      tree_image_visual="" 
      tree_material="snow" 
      tree_probability="0" 
      tree_radius_high="0.414286" 
      tree_radius_low="0.228571" 
      tree_width="76.1143" 
      visual_color="0xffb89f6c" 
      visual_offset_x="3" 
      visual_offset_y="7.5" 
      is_grass="1"
      grass_requires_neighbors="1"
      material_on_top_of="wood_static"
    ></VegetationComponent>

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
      tree_extra_y="2" 
      tree_image_file="data/vegetation/mushroom_small_0$[1-5].png" 
      tree_image_visual="" 
      tree_material="fungus_loose" 
      tree_probability="0.128571" 
      tree_radius_high="0.414286" 
      tree_radius_low="0.328571" 
      tree_width="18.1143" 
      visual_color="0xffb89f6c" 
      visual_offset_x="3" 
      visual_offset_y="1"
	  material_on_top_of="rock_static_grey"
	  >
    </VegetationComponent>
	
	<VegetationComponent 
      _enabled="1" 
      is_visual="0" 
      rand_seed="1245.86" 
      tree_extra_y="2" 
      tree_image_file="data/vegetation/mushroom_small_0$[6-9].png" 
      tree_image_visual="" 
      tree_material="fungus_loose" 
      tree_probability="0.128571" 
      tree_radius_high="0.414286" 
      tree_radius_low="0.328571" 
      tree_width="16.1143" 
      visual_color="0xffb89f6c" 
      visual_offset_x="3" 
      visual_offset_y="1"
	  material_on_top_of="rock_static_grey"
	  >
    </VegetationComponent>
	
	<VegetationComponent 
      _enabled="1" 
      is_visual="1" 
      rand_seed="507812" 
      tree_extra_y="-1" 
      tree_image_file="data/vegetation/redplant_0$[1-4].xml" 
      tree_image_visual="" 
      tree_material="plant_material_red" 
      tree_probability="0.728571" 
      tree_radius_high="0.214286" 
      tree_radius_low="0.1027" 
      tree_width="28.571" 
      visual_color="0xff4d5d44" 
      visual_offset_x="15" 
      visual_offset_y="32" 
	  >
    </VegetationComponent>
    
  </Materials>

</Biome>
```