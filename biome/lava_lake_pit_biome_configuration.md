---
title: Lava Lake Pit Biome Configuration
category: biome
---

# Lava Lake Pit Biome Configuration

This document details the configuration for the `lavalake_pit` biome in Noita, focusing on its topological properties, material distribution, and associated scripts.

## Topology

The `Topology` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes

| Attribute | Description | Value |
|---|---|---|
| `name` | Internal name for this topology configuration. | `_EMPTY_` |
| `type` | Type of biome generation. | `BIOME_WANG_TILE` |
| `background_image` | Path to the main background image. | `data/weather_gfx/background_cave_04_alt.png` |
| `background_edge_left`, `_right`, `_top`, `_bottom` | Paths to specific edge textures for the background. | `data/weather_gfx/edges/background_cave_04_alt_*.png` |
| `background_edge_priority` | Determines the layering of background elements. | `10` |
| `lua_script` | Path to the Lua script that governs biome behavior. | `data/scripts/biomes/lavalake_pit.lua` |
| `wang_map_width`, `wang_map_height` | Dimensions of the Wang tile map used for generation. | `256`, `256` |
| `coarse_map_force_terrain` | Forces terrain generation on the coarse map. | `1` |
| `audio_ambience` | The ambient sound theme for this biome. | `cave` |
| `skip_edge_textures` | Skips rendering edge textures for this biome. | `1` |

## Materials

The `Materials` element defines the various materials that can spawn within this biome and their distribution parameters.

### Material Components

Each `MaterialComponent` defines a specific material and how it's placed.

| Attribute | Description | Value |
|---|---|---|
| `name` | Internal name for the material component. | Varies (e.g., `coal`, `rock_hard`, `copper`) |
| `material_name` | The actual material ID used in the game. | Varies (e.g., `coal`, `rock_hard`, `copper`) |
| `is_rare` | Whether this material is considered rare. | `0` or `1` |
| `limit_min_y`, `limit_max_y` | Vertical bounds for material placement. | Varies (e.g., `100`, `2048`, `750`) |
| `material_min`, `material_max` | The minimum and maximum density/probability of the material. | Varies (e.g., `0.51` - `0.55` for coal) |
| `rare_polka_probability` | Probability of using the "polka" distribution pattern for rare materials. | Varies (e.g., `0.160871`) |
| `rare_polka_radius_low`, `rare_polka_radius_high` | Defines the radius range for the polka distribution. | Varies (e.g., `0.357143` - `0.771429`) |
| `rare_scale_x`, `rare_scale_y` | Scaling factors for the material's distribution pattern. | Varies (e.g., `0.0100004` - `0.00357165`) |
| `rare_use_perlin` | Whether to use Perlin noise for distribution. | `0` or `1` |
| `rare_use_polka` | Whether to use the polka distribution pattern. | `1` |

#### Example Material Components:

*   **Coal (Rare):** Appears with a probability between `0.51` and `0.55`, using a polka distribution with specific radius and scale parameters.
*   **Hard Rock:** A common material with a density range of `0.53` to `0.95`, also utilizing polka distribution.
*   **Hard Rock Border:** Similar to hard rock but with a higher density range (`0.9` to `3.5`).
*   **Copper (Rare):** Found at higher elevations (`limit_min_y="750"`) with a density between `1.05` and `1.25`, using Perlin and polka distribution.

---
```xml
<Biome>
  <Topology 
    name="_EMPTY_"
    type="BIOME_WANG_TILE"
    background_image="data/weather_gfx/background_cave_04_alt.png"
    background_edge_left="data/weather_gfx/edges/background_cave_04_alt_left.png"
    background_edge_right="data/weather_gfx/edges/background_cave_04_alt_right.png"
    background_edge_top="data/weather_gfx/edges/background_cave_04_alt_top.png"
    background_edge_bottom="data/weather_gfx/edges/background_cave_04_alt_bottom.png"
    background_edge_priority="10"
    wang_template_file="" 
    lua_script="data/scripts/biomes/lavalake_pit.lua"
    wang_map_width="256"
    wang_map_height="256"
    limit_background_image="0"
    coarse_map_force_terrain="1"
    audio_ambience="cave"
    noise_biome_edges="0"
    skip_edge_textures="1"
    >
  </Topology>

  <Materials 
    name="lavalake" 
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
      is_rare="0" 
      limit_max_y="2048" 
      limit_min_y="100" 
      limit_y="0" 
      material_index="10" 
      material_max="3.5" 
      material_min="0.9" 
      material_name="rock_hard_border" 
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
  </Materials>

</Biome>
```