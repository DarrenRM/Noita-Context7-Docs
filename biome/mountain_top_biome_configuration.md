---
title: Mountain Top Biome Configuration
category: biome
---

---

# Mountain Top Biome Configuration

This document outlines the configuration for the "Mountain Top" biome in Noita, focusing on its initialization and spawning logic.

## Core Biome Initialization

The `init` function is the primary entry point for setting up the Mountain Top biome.

### Key Initialization Parameters

| Parameter | Description                                                                 |
| :-------- | :-------------------------------------------------------------------------- |
| `x`, `y`  | The world coordinates for the biome's origin.                               |
| `w`, `h`  | The width and height of the biome area (often implicitly handled by pixel scenes). |

### Pixel Scene Loading

The biome's visual structure is defined by pixel scenes.

| Scene File Path                     | Description