---
title: Snowy Rock 04 Prop
category: entities
---

# Snowy Rock 04 Prop

This document describes the `snowy_rock_04.xml` entity, a prop found in the overworld.

## Key Components

### PixelSceneComponent
This component defines the visual representation of the prop.

*   **pixel_scene**: `data/biome_impl/overworld/snowy_rock_04.png` - The primary image for the prop.
*   **pixel_scene_visual**: `data/biome_impl/overworld/snowy_rock_04_visual.png` - A secondary visual layer, likely for effects or detail.
*   **offset\_x**: `-40` - Horizontal offset for the prop's placement.
*   **offset\_y**: `-12` - Vertical offset for the prop's placement.

### LifetimeComponent
This component dictates how long the prop persists.

*   **lifetime**: `2` - The prop will exist for 2 seconds before disappearing.