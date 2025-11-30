---
title: Coalmine Extra Wang Tile Layers
category: data
---

# Coalmine Extra Wang Tile Layers

This documentation describes extra Wang tile layers specifically designed for the Coalmine biome in Noita. These layers are intended to add visual variety and detail to this specific environment.

## Key Features and Limitations

*   **Coalmine Specific:** These Wang tile layers are hardcoded to load *only* within the Coalmine biome.
*   **Ramp Pixel Removal:** Ramp pixels are automatically removed by the system, and this behavior is also specific to the Coalmine.
*   **Extensibility:** The current implementation is limited to the Coalmine. If these features are desired in other biomes, the underlying code would need modification to support broader integration.

## Usage

These Wang tile layers are intended to be placed within the `data/wang_tiles/extra_layers/` directory and will be loaded by the game when the player is in the Coalmine biome. Their primary purpose is to enhance the visual appearance of this area.

## Technical Notes

*   **Hardcoded Biome Loading:** The mechanism for loading these tiles is tied directly to the Coalmine biome identifier.
*   **Ramp Pixel Handling:** The game's logic for processing ramp pixels has been adjusted to accommodate these extra layers within the Coalmine context.

---