---
title: Snowcave Biome Configuration
category: biome
---

# Snowcave Biome Configuration

This document details the configuration for the Snowcave biome in Noita, focusing on its visual and material properties.

## Topology

The `Topology` element defines the core visual and structural aspects of the biome.

### Key Attributes

| Attribute | Description |
|---|---|
| `name` | Internal identifier for the biome (e.g., `$biome_snowcave`). |
| `type` | Specifies the biome generation method, `BIOME_WANG_TILE` indicates it uses Wang tiles. |
| `background_image` | Path to the main background image for the biome. |
| `background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom` | Paths to images used for background edges, creating seamless transitions. |
| `background_edge_priority` | Determines the rendering order of background edges. |
| `wang_template_file` | Path to the Wang tile template image used for generating the biome's structure. |
| `lua_script` | Path to the Lua script that controls biome-specific behaviors and generation. |
| `wang_map_width`, `wang_map_height` | Dimensions of the Wang tile map used for generation. |
| `audio_music_2` | Name of the music track associated with this biome. |
| `audio_ambience` | Name of the ambient soundscape for this biome. |

## Materials

The `Materials` element defines the various materials that can spawn within the Snowcave biome and their properties.

### Material Components

Each `MaterialComponent` defines a specific material and how it's distributed.

| Attribute | Description |
|---|---|
| `_enabled` | Whether this material component is active (1) or not (0). |
| `is_rare` | Indicates if the material is considered rare (1) or common (0). |
| `limit_max_y`, `limit_min_y`, `limit_y` | Vertical boundaries within which this material can spawn. |
| `material_index` | Internal index for the material. |
| `material_max`, `material_min` | Maximum and minimum density or quantity of the material. |
| `material_name` | The internal name of the material (e.g., `snowrock_static`, `snow_static`, `ice_static`, `gold`). |
| `rare_polka_is_boxed`, `rare_polka_probability`, `rare_polka_radius_high`, `rare_polka_radius_low` | Parameters controlling the distribution pattern of rare materials (polka-dot like). |
| `rare_required_max`, `rare_required_min` | Minimum and maximum density requirements for rare materials. |
| `rare_scale_x`, `rare_scale_y` | Scaling factors for the rare material's distribution pattern. |
| `rare_use_perlin` | Whether Perlin noise is used for distribution (1) or not (0). |
| `rare_use_polka` | Whether the polka-dot distribution method is used (1) or not (0). |

#### Example Material Components:

*   **`snowrock_static`**: A common static snow rock material.
*   **`snow_static`**: A common static snow material.
*   **`snow_sticky`**: A sticky variant of snow, with different vertical limits.
*   **`ice_static`**: A rare static ice material, with specific distribution parameters.
*   **`gold`**: A rare gold material, often used for biome modifiers, with `material_max` and `material_min` initially set to 0 for dynamic generation.

```xml
<Biome>
  <Topology 
    name="$biome_snowcave"
    type="BIOME_WANG_TILE"
    background_image="data/weather_gfx/background_snowcave.png"
    background_edge_left="data/weather_gfx/edges/background_snowcave_left.png"
    background_edge_right="data/weather_gfx/edges/background_snowcave_right.png"
    background_edge_top="data/weather_gfx/edges/background_snowcave_top.png"
    background_edge_bottom="data/weather_gfx/edges/background_snowcave_bottom.png"
    background_edge_priority="10"     
    wang_template_file="data/wang_tiles/snowcave.png" 
    lua_script="data/scripts/biomes/snowcave.lua"
    wang_map_width="256"
    wang_map_height="256"
    audio_music_2="snowcave"
    audio_ambience="snowcave">
  </Topology>

  <Materials name="snowcave">
	<MaterialComponent 
      _enabled="1" 
      is_rare="0" 
      limit_max_y="2048" 
      limit_min_y="100" 
      material_index="9" 
      material_max="3.6" 
      material_min="0.9" 
      material_name="snowrock_static" 
      rare_use_polka="1" >
    </MaterialComponent>
	
	<MaterialComponent 
      _enabled="1" 
      is_rare="0" 
      limit_max_y="2048" 
      limit_min_y="100" 
      material_index="10" 
      material_max="1.05" 
      material_min="0.53" 
      material_name="snow_static" 
      rare_use_polka="1" >
    </MaterialComponent>
	
	<MaterialComponent 
      _enabled="1" 
      is_rare="0" 
      limit_max_y="2248" 
      limit_min_y="50" 
      material_name="snow_sticky" >
    </MaterialComponent>

    <MaterialComponent 
      _enabled="1" 
      is_rare="1" 
      limit_max_y="2048" 
      limit_min_y="100" 
      material_index="5" 
      material_max="3.5" 
      material_min="0.9" 
      material_name="ice_static" 
      rare_polka_probability="0.1" 
      rare_polka_radius_high="1.8" 
      rare_polka_radius_low="0.8" 
      rare_use_polka="1" >
    </MaterialComponent>
    
    <MaterialComponent 
      _enabled="1" 
      is_rare="1" 
      limit_max_y="2048" 
      limit_min_y="750" 
      material_index="9" 
      material_max="0" 
      material_min="0" 
      material_name="gold" 
      rare_polka_probability="0.357143" 
      rare_polka_radius_high="0.564286" 
      rare_polka_radius_low="0.328571" 
      rare_use_perlin="1" 
      rare_use_polka="1" >
    </MaterialComponent>
  </Materials>
</Biome>
```