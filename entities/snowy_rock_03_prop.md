---
title: Snowy Rock 03 Prop
category: entities
---

# Snowy Rock 03 Prop

This document describes the `snowy_rock_03.xml` entity, a prop found in the overworld.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag.

### Key Components

*   **`<PixelSceneComponent>`**: This component defines the visual representation of the prop.
    *   `pixel_scene`: Specifies the primary pixel art file for the prop (`data/biome_impl/overworld/snowy_rock_03.png`).
    *   `pixel_scene_visual`: Points to an optional visual layer, likely for effects or variations (`data/biome_impl/overworld/snowy_rock_03_visual.png`).
    *   `offset_x`: Horizontal offset for the prop's placement (`-44`).
    *   `offset_y`: Vertical offset for the prop's placement (`-20`).

*   **`<LifetimeComponent>`**: This component dictates how long the prop exists.
    *   `lifetime`: The duration in seconds the prop will persist (`2`).

```xml
<Entity>
	<PixelSceneComponent
		pixel_scene="data/biome_impl/overworld/snowy_rock_03.png"
		pixel_scene_visual="data/biome_impl/overworld/snowy_rock_03_visual.png"
		offset_x="-44"
		offset_y="-20"
		>
	</PixelSceneComponent>

	<LifetimeComponent
		lifetime="2"
		>
	</LifetimeComponent>
</Entity>
```