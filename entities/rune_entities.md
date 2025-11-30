---
title: Rune Entities
category: entities
---

# Rune Entities

This documentation describes the entities related to runes in Noita, focusing on their visual representation.

## Rune Entity

The primary entity for runes defines their visual appearance.

### Key Attributes

*   **SpriteComponent**: This component handles the visual rendering of the rune.
    *   `image_file`: Specifies the graphical asset used for the rune. In this case, it points to `data/buildings_gfx/runes.xml`.
    *   `offset_x`, `offset_y`: Define the sprite's position relative to the entity's origin.
    *   `emissive`: A value of `1` indicates that the sprite emits light, making the rune glow.

```xml
<Entity>
  <SpriteComponent 
		image_file="data/buildings_gfx/runes.xml" 
		offset_x="0"
		offset_y="0"
		emissive="1"
		>
	</SpriteComponent>
</Entity>
```