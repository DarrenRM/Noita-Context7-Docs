---
title: Fog of War Radius Entity
category: entities
---

# Fog of War Radius Entity

This entity defines a localized area that affects the fog of war. It's primarily used to create "holes" or clearings in the fog of war, allowing players to see further in specific areas.

## Entity Structure

The entity consists of two main components:

### FogOfWarRadiusComponent

This component controls the core fog of war clearing behavior.

| Attribute | Description                                     | Key Values |
| :-------- | :---------------------------------------------- | :--------- |
| `_enabled` | Whether the component is active.                | `1`        |
| `radius`   | The radius (in pixels) of the fog of war clearing. | `200`      |

### SpriteComponent

This component defines the visual representation of the fog of war clearing.

| Attribute         | Description                                                                 | Key Values                                     |
| :---------------- | :-------------------------------------------------------------------------- | :--------------------------------------------- |
| `_enabled`        | Whether the sprite is active.                                               | `1`                                            |
| `alpha`           | The transparency of the sprite.                                             | `0.8`                                          |
| `image_file`      | The path to the image file used for the sprite.                             | `data/particles/torch_fog_of_war_hole.xml`     |
| `smooth_filtering`| Enables smooth filtering for the sprite.                                    | `1`                                            |
| `fog_of_war_hole` | **Crucial:** Marks this sprite as a fog of war clearing.                    | `1`                                            |
| `has_special_scale`| Whether to apply special scaling to the sprite.                             | `1`                                            |
| `special_scale_x` | The X-axis scaling factor for the sprite.                                   | `4`                                            |
| `special_scale_y` | The Y-axis scaling factor for the sprite.                                   | `4`                                            |

## Usage Example

This entity is typically placed in the game world to create persistent or temporary clearings in the fog of war. For instance, it could be attached to a light source to make the area around it visible.

```xml
<Entity >
  <FogOfWarRadiusComponent
    _enabled="1" 
    radius="200"
	 >
  </FogOfWarRadiusComponent>

	  <SpriteComponent 
        _enabled="1" 
	    alpha="0.8"
	    image_file="data/particles/torch_fog_of_war_hole.xml"
	    smooth_filtering="1"
	    fog_of_war_hole="1"
	    has_special_scale="1"
	    special_scale_x="4"
	    special_scale_y="4" >
	</SpriteComponent>
</Entity>
```