---
title: Lake Statue Biome Splice
category: biome
---

# Lake Statue Biome Splice

This document describes the configuration for splicing the "Lake Statue" biome into Noita. It utilizes a pixel scene definition to define the biome's layout and elements.

## Core Configuration

The primary function of this file is to execute a `wizard_physics.exe` command to splice a pixel scene.

### `wizard_physics.exe -splice_pixel_scene`

This command is used to integrate a visual representation of a biome into the game.

*   **`data/biome_impl/spliced/lake_statue.png`**: This is the pixel scene file that defines the visual layout and elements of the Lake Statue biome. The game interprets the colors and patterns within this PNG to generate the biome.
*   **`-x -14848`**: Specifies the horizontal offset (X-coordinate) where this biome splice will be placed in the game world.
*   **`-y 0`**: Specifies the vertical offset (Y-coordinate) where this biome splice will be placed in the game world.

## Execution Context

The `pushd` and `popd` commands are used to manage the directory context for the execution of `wizard_physics.exe`.

*   **`pushd ..\..\..\`**: Changes the current directory to the root of the Noita data directory. This ensures that `wizard_physics.exe` can be found and executed correctly, and that relative paths within the command are resolved from the correct base.
*   **`popd`**: Restores the previous directory context after the `wizard_physics.exe` command has completed.