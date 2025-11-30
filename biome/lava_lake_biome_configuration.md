---
title: Lava Lake Biome Configuration
category: biome
---

# Lava Lake Biome Configuration

This document details the configuration for the Lava Lake biome in Noita, focusing on its visual and material properties.

## Topology

The `<Topology>` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes

| Attribute | Description |
|---|---|
| `name` | Internal identifier for the topology, set to `_EMPTY_` for this biome. |
| `type` | Specifies the biome generation type, `BIOME_WANG_TILE` indicates it uses Wang tiles for generation. |
| `background_image` | Path to the main background image for the biome. |
| `background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom` | Paths to specific edge graphics for seamless background tiling. |
| `background_edge_priority` | Determines the rendering order of background edges. |
| `lua_script` | Path to the Lua script that governs biome-specific behaviors and generation logic. |
| `wang_map_width`, `wang_map_height` | Dimensions of the Wang tile map used for biome generation. |
| `audio_ambience` | The sound ambience associated with this biome (e.g., "cave"). |
| `coarse_map_force_terrain` | Forces terrain generation on the coarse map. |
| `skip_edge_textures` | Skips rendering of edge textures. |

## Materials

The `<Materials>` element defines the distribution and properties of various materials within the biome.

### Material Components

Each `<MaterialComponent>` defines a specific material's presence and characteristics.

| Attribute | Description |
|---|---|
| `name` | The name of the material (e.g., "coal", "rock_hard", "copper"). |
| `is_rare` | Whether the material is considered rare within the biome (1 for rare, 0 for common). |
| `limit_max_y`, `limit_min_y`, `limit_y` | Vertical limits for the material's placement. `limit_y` can be 0 for no specific vertical limit, or 1 to use `limit_min_y` and `limit_max_y`. |
| `material_index` | An index used internally for material processing. |
| `material_max`, `material_min` | The maximum and minimum density or probability of the material appearing. |
| `rare_polka_is_boxed`, `rare_polka_probability`, `rare_polka_radius_high`, `rare_polka_radius_low` | Attributes related to a "polka" distribution pattern for rare materials, controlling its appearance and clustering. |
| `rare_required_max`, `rare_required_min` | Minimum and maximum requirements for a rare material to be considered. |
| `rare_scale_x`, `rare_scale_y` | Scaling factors for the rare material's distribution pattern. |
| `rare_use_perlin`, `rare_use_polka` | Flags to enable Perlin noise or polka distribution for rare materials. |

#### Example Material Components:

*   **Coal:** Appears with varying probabilities and scales, sometimes using Perlin noise for distribution.
*   **Rock Hard:** A common material with specific density ranges and polka distribution.
*   **Rock Hard Border:** Similar to `rock_hard` but potentially with different density or border-specific properties.
*   **Copper:** A rare material with specific vertical limits and a polka distribution pattern.

---