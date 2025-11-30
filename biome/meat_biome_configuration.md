---
title: Meat Biome Configuration
category: biome
---

# Meat Biome Configuration

This document details the configuration for the "Meat" biome in Noita, focusing on its visual, auditory, and material generation properties.

## Topology

The `<Topology>` tag defines the fundamental characteristics of the biome's generation and appearance.

### Key Attributes:

*   **`name`**: `$biome_meat` - Internal identifier for this biome.
*   **`type`**: `BIOME_WANG_TILE` - Indicates this biome uses Wang tiles for generation.
*   **`background_image`**: `data/weather_gfx/background_the_end.png` - The primary background image for this biome.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: Paths to specific edge graphics for the background.
*   **`background_edge_priority`**: `9` - Determines the rendering order of background edges.
*   **`wang_template_file`**: `data/wang_tiles/meat.png` - The image file containing the Wang tile patterns for this biome.
*   **`lua_script`**: `data/scripts/biomes/meat.lua` - The script responsible for biome-specific logic and generation.
*   **`wang_map_width`, `wang_map_height`**: `256` - Dimensions of the generated Wang tile map.
*   **`audio_music_2`**: `rainforest` - The music track associated with this biome.
*   **`audio_music_energy_coeff`**: `2` - A coefficient affecting music energy.
*   **`audio_music_forced_quietness_duration_seconds`**: `4` - Duration for forced quietness in music.
*   **`audio_ambience`**: `rainforest` - The ambient soundscape for this biome.

## Materials

The `<Materials>` tag defines the types and distribution of materials within the biome.

### Key Attributes:

*   **`name`**: `meat` - The identifier for this material set.

### Material Components:

Each `<MaterialComponent>` defines a specific material's properties and how it's generated.

#### MaterialComponent 1 (Primary Meat)

*   **`_enabled`**: `1` - Component is active.
*   **`is_rare`**: `0` - This is a common material.
*   **`limit_max_y`**: `424.229` - Maximum Y-coordinate for generation.
*   **`limit_min_y`**: `-1024` - Minimum Y-coordinate for generation.
*   **`material_index`**: `10` - Internal index for the material.
*   **`material_max`**: `0.66` - Maximum density/value for this material.
*   **`material_min`**: `0.57` - Minimum density/value for this material.
*   **`material_name`**: `meat_static` - The name of the material.
*   **`rare_use_polka`**: `1` - Uses a polka distribution pattern.
*   **`rare_polka_probability`**: `0.2` - Probability of a polka dot appearing.
*   **`rare_polka_radius_high`**: `0.65` - Higher end of the polka dot radius.
*   **`rare_polka_radius_low`**: `0.2` - Lower end of the polka dot radius.
*   **`rare_required_max`**: `10` - Maximum requirement for polka generation.
*   **`rare_required_min`**: `0.2` - Minimum requirement for polka generation.
*   **`rare_scale_x`, `rare_scale_y`**: `0.05` - Scaling factors for the polka pattern.

#### MaterialComponent 2 (Rare Gold)

*   **`_enabled`**: `1` - Component is active.
*   **`is_rare`**: `1` - This is a rare material.
*   **`limit_max_y`**: `2048` - Maximum Y-coordinate for generation.
*   **`limit_min_y`**: `100` - Minimum Y-coordinate for generation.
*   **`material_index`**: `10` - Internal index for the material.
*   **`material_max`**: `1.2` - Maximum density/value for this material.
*   **`material_min`**: `1.1` - Minimum density/value for this material.
*   **`material_name`**: `gold` - The name of the material.
*   **`rare_use_polka`**: `1` - Uses a polka distribution pattern.
*   **`rare_polka_probability`**: `0.357143` - Probability of a polka dot appearing.
*   **`rare_polka_radius_high`**: `0.464286` - Higher end of the polka dot radius.
*   **`rare_polka_radius_low`**: `0.0428571` - Lower end of the polka dot radius.
*   **`rare_required_max`**: `10` - Maximum requirement for polka generation.
*   **`rare_required_min`**: `0.371429` - Minimum requirement for polka generation.
*   **`rare_scale_x`, `rare_scale_y`**: `0.0214286` - Scaling factors for the polka pattern.

#### MaterialComponent 3 (Secondary Meat)

*   **`_enabled`**: `1` - Component is active.
*   **`is_rare`**: `0` - This is a common material.
*   **`limit_max_y`**: `2048` - Maximum Y-coordinate for generation.
*   **`limit_min_y`**: `100` - Minimum Y-coordinate for generation.
*   **`material_index`**: `10` - Internal index for the material.
*   **`material_max`**: `3.5` - Maximum density/value for this material.
*   **`material_min`**: `0.65` - Minimum density/value for this material.
*   **`material_name`**: `meat_static` - The name of the material.
*   **`rare_use_perlin`**: `0` - Does not use Perlin noise for distribution.
*   **`rare_use_polka`**: `0` - Does not use a polka distribution pattern.