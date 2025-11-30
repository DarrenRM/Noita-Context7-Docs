---
title: Mountain Lake Biome Splice
category: biome
---

# Mountain Lake Biome Splice

This document describes the configuration for the "Mountain Lake" biome splice in Noita, as defined by the `_mountain_lake.bat` file. This file is responsible for generating a specific biome within the game world.

## Biome Generation

The `_mountain_lake.bat` file utilizes a `wizard_physics.exe` command to splice a pixel scene into the game's data.

### Key Parameters

*   **`data/biome_impl/spliced/mountain_lake.png`**: This is the primary image file that defines the visual and structural elements of the Mountain Lake biome. The game engine will interpret this pixel data to generate the biome.
*   **`-x 2560`**: Specifies the X-coordinate offset where the `mountain_lake.png` scene will be spliced into the larger biome map.
*   **`-y 0`**: Specifies the Y-coordinate offset where the `mountain_lake.png` scene will be spliced into the larger biome map.

## Purpose

This splice operation is a method for procedurally generating or defining specific biome layouts within Noita. By using a pixel image as a blueprint, developers can create detailed and unique environments for players to explore. The "Mountain Lake" biome likely represents a distinct geographical area with specific visual themes and potential gameplay elements associated with it.