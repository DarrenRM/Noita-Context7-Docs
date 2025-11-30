---
title: Skull Biome Splice Configuration
category: biome
---

```

# Skull Biome Splice Configuration

This document details the configuration for splicing the "Skull" biome into the Noita world. It utilizes a batch script to execute a Noita tool for this purpose.

## Core Functionality

The primary function of this script is to integrate a specific biome image (`skull.png`) into the game's world at defined coordinates.

### Key Attributes

*   **`wizard_physics.exe -splice_pixel_scene`**: This is the Noita tool command used to perform the biome splicing operation. It takes an image file as input and integrates it as a biome.
*   **`data/biome_impl/spliced/skull.png`**: The image file representing the "Skull" biome. This image defines the visual appearance and potentially the underlying tile data of the biome.
*   **`-x 14645`**: The X-coordinate where the top-left corner of the "Skull" biome will be placed in the game world.
*   **`-y 18395`**: The Y-coordinate where the top-left corner of the "Skull" biome will be placed in the game world.

## Execution Context

The `pushd` and `popd` commands are used to manage the current directory for the execution of the `wizard_physics.exe` command, ensuring it runs from the correct root directory of the Noita data.

### Directory Management

*   **`pushd ..\..\..\`**: Changes the current directory to the root of the Noita data directory (three levels up from `data/biome_impl/spliced/`). This is crucial for `wizard_physics.exe` to locate necessary game files and execute correctly.
*   **`popd`**: Restores the previous directory after the `wizard_physics.exe` command has finished.

## Summary

This batch script is a straightforward command to inject a pre-designed biome into the Noita world. The `skull.png` image defines the biome's appearance, and the `-x` and `-y` parameters dictate its precise location. This is a fundamental method for custom biome integration in Noita modding.