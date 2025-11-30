---
title: Safe Haven Building
category: entities
---

# Safe Haven Building

This entity defines a "safe haven" area within the game world. It's primarily used for visual representation and a temporary safe zone.

## Key Components

### PixelSceneComponent
This component handles the visual aspects of the safe haven.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `pixel_scene`       | Path to the main pixel art for the safe haven.                           |
| `pixel_scene_visual`| Path to the visual layer of the safe haven's pixel art.                  |
| `pixel_scene_background` | Path to the background layer of the safe haven's pixel art.           |
| `offset_x`          | Horizontal offset for the placement of the pixel scene.                  |
| `offset_y`          | Vertical offset for the placement of the pixel scene.                    |
| `skip_biome_checks` | If set to `1`, biome-specific checks are ignored for this entity.        |

### LifetimeComponent
This component determines how long the safe haven entity persists.

| Attribute | Description                                  |
| :-------- | :------------------------------------------- |
| `lifetime`| The duration (in seconds) the entity exists. |