---
title: Light Entity
category: entities
---

# Light Entity

This entity defines a light source within the game world. It's primarily used for visual effects and can influence the fog of war.

## Components

### LightComponent

This component controls the properties of the light emitted by the entity.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `_enabled` | Whether the light component is active (1/0).    |
| `radius`   | The radius of the light's influence in pixels. |

### _Transform

This component handles the spatial transformation of the entity.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `scale.x`  | The scaling factor along the X-axis.            |
| `scale.y`  | The scaling factor along the Y-axis.            |

### SpriteComponent

This component defines the visual representation of the entity.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `alpha`          | The transparency of the sprite (0.0 to 1.0).                             |
| `image_file`     | The path to the image file used for the sprite.                          |
| `smooth_filtering` | Enables smooth filtering for the sprite (1/0).                           |
| `fog_of_war_hole` | If set to 1, this sprite will create a "hole" in the fog of war.         |

```xml
<Entity>
	<LightComponent 
		_enabled="1"
		radius="200" >
	</LightComponent>
	
	<_Transform
        scale.x="5" scale.y="5" >
    </_Transform>

	<SpriteComponent 
		alpha="0.55"
		image_file="data/particles/fog_of_war_hole_128.xml"
		smooth_filtering="1"
		fog_of_war_hole="1" >
	</SpriteComponent>
</Entity>
```