---
title: Wizard Cave Entrance Biome
category: biome
---

# Wizard Cave Entrance Biome

This document describes the configuration for the Wizard Cave Entrance biome in Noita, focusing on key attributes relevant for AI-assisted modding.

## Topology

The `Topology` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes:

*   **`name`**: `_EMPTY_` - Indicates this is a base topology definition.
*   **`background_image`**: `data/weather_gfx/background_crypt.png` - The primary background image for this biome.
*   **`background_edge_left`**, **`background_edge_right`**, **`background_edge_top`**, **`background_edge_bottom`**: These specify the edge graphics for the background, contributing to the visual continuity.
*   **`background_edge_priority`**: `10` - Determines the rendering order of background edges. Higher values are drawn on top.
*   **`limit_background_image`**: `0` - Controls whether the background image is limited by the biome's boundaries. `0` means it's not limited.
*   **`lua_script`**: `data/scripts/biomes/wizardcave_entrance.lua` - The associated Lua script that governs the biome's behavior, entity spawning, and other dynamic elements.
*   **`audio_ambience`**: `wandcave` - Specifies the ambient soundscape for this biome.

## Materials

The `Materials` element defines the types of materials that can be found or generated within the biome.

### Key Attributes:

*   **`name`**: `solid_wall` - This indicates that the primary material for solid structures in this biome is `solid_wall`. Further material properties would typically be defined within this tag or through associated scripts.

---