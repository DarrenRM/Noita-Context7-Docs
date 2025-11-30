---
title: Moon Biome Splice Configuration
category: biome
---

# Moon Biome Splice Configuration

This document details the configuration for splicing the Moon biome into Noita. It outlines the process of using the `wizard_physics.exe` tool to generate biome data from a pixel scene.

## Core Functionality

The primary function of this configuration is to define how the Moon biome is integrated into the game world. This is achieved by referencing a pixel scene (`moon.png`) and specifying its placement within the game's coordinate system.

### Key Attributes

*   **`splice_pixel_scene`**: Specifies the path to the pixel scene file that defines the visual and structural elements of the biome.
    *   Value: `data/biome_impl/spliced/moon.png`
*   **`-x`**: The horizontal offset for placing the biome.
    *   Value: `0`
*   **`-y`**: The vertical offset for placing the biome.
    *   Value: `-26112`

## Execution Context

The `pushd` and `popd` commands are used to manage the directory context for the execution of the `wizard_physics.exe` tool. This ensures that the tool can correctly locate the necessary files and execute its operations.

### Commands

*   **`pushd ..\..\..\`**: Changes the current directory to the parent directory three levels up. This is likely done to set the root directory for the `wizard_physics.exe` tool.
*   **`wizard_physics.exe -splice_pixel_scene data/biome_impl/spliced/moon.png -x 0 -y -26112`**: Executes the `wizard_physics.exe` tool with specific arguments to perform the biome splicing operation.
*   **`popd`**: Restores the previous directory context.