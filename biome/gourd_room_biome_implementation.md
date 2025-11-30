---
title: Gourd Room Biome Implementation
category: biome
---

# Gourd Room Biome Implementation

This document details the implementation of the "Gourd Room" biome within Noita, as defined by the `_gourd.bat` script. This script orchestrates the placement and configuration of the biome's visual and interactive elements.

## Core Functionality

The `_gourd.bat` script utilizes `wizard_physics.exe` to splice a pre-defined biome scene (`gourd_room.png`) into the game world at specific coordinates.

### Key Parameters

*   **`splice_pixel_scene data/biome_impl/spliced/gourd_room.png`**: This is the primary command that instructs the game to load and integrate the `gourd_room.png` image as a biome layer. This image likely defines the visual layout, terrain, and potentially entity placements within the Gourd Room.
*   **`-x -16896 -y -7168`**: These parameters specify the absolute world coordinates where the Gourd Room biome will be placed. This ensures consistent positioning of this biome within the game's generated world.
*   **`-debug 1`**: This flag enables debug output during the splicing process, which can be helpful for modders to diagnose issues or understand the biome's integration.

## Biome Characteristics (Inferred)

While the script itself is focused on placement, the `gourd_room.png` asset implies the following characteristics for the Gourd Room biome:

### Visuals and Layout

*   **Thematic Elements**: The name "Gourd Room" strongly suggests a biome with a distinct visual theme, likely incorporating gourd-like structures, organic shapes, and potentially a specific color palette.
*   **Terrain**: The `gourd_room.png` will define the shape and composition of the terrain within this biome, including walls, floors, and any unique geological formations.
*   **Environmental Hazards/Features**: It's probable that this biome includes unique environmental features or hazards related to its theme, such as specific liquids, gases, or interactive objects.

### Potential Entity Spawns

*   **Thematic Enemies**: The Gourd Room may be populated with specific enemies that fit its thematic design.
*   **Unique Items/Collectibles**: The biome could contain special items, power-ups, or lore-related collectibles.
*   **Environmental Interactions**: Interactive elements within the biome might be tied to its theme, such as mechanisms or puzzles.

## Modding Considerations

*   **Asset Replacement**: Modders can replace `gourd_room.png` with their own custom biome designs to alter the appearance and layout of the Gourd Room.
*   **Coordinate Adjustment**: The `-x` and `-y` coordinates can be modified to reposition the Gourd Room biome within the world.
*   **Debug Information**: The `-debug 1` flag is valuable for troubleshooting when integrating custom biome assets or modifying the splicing process.

---