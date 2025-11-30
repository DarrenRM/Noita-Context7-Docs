---
title: Sand Pile 02 Entity
category: entities
---

# Sand Pile 02 Entity

This document describes the `sand_pile_02.xml` entity, a prop found in the overworld.

## Entity Definition

The `sand_pile_02.xml` file defines a simple prop entity with visual representation and a limited lifespan.

### Key Components

*   **PixelSceneComponent**: This component handles the visual aspect of the entity.
    *   `pixel_scene`: Specifies the image file used for the prop's appearance (`data/biome_impl/overworld/sand_pile_02.png`).
    *   `offset_x`: Horizontal offset for the sprite.
    *   `offset_y`: Vertical offset for the sprite.

*   **LifetimeComponent**: This component determines how long the entity persists in the game world.
    *   `lifetime`: The duration in seconds the entity will exist before disappearing (set to `2`).

### XML Structure

```xml
<Entity>
	<PixelSceneComponent
		pixel_scene="data/biome_impl/overworld/sand_pile_02.png"
		pixel_scene_visual=""
		offset_x="-11"
		offset_y="-11"
		>
	</PixelSceneComponent>

	<LifetimeComponent
		lifetime="2"
		>
	</LifetimeComponent>
</Entity>
```