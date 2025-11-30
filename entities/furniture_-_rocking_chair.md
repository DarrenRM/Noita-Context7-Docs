---
title: Furniture - Rocking Chair
category: guides
---

<Entity name="unknown" >
	<Base file="data/entities/base_item_physics2.xml" >
		<PhysicsImageShapeComponent 
			image_file="data/props_gfx/furniture_rocking_chair.png"
			material="wood_prop"
			>
		</PhysicsImageShapeComponent>
	</Base>
</Entity>
```

---
title: Furniture - Rocking Chair
category: entities
---

# Furniture - Rocking Chair

This document describes the `furniture_rocking_chair.xml` entity, a basic prop for Noita.

## Key Attributes

*   **`name`**: "unknown" - This is a placeholder and should ideally be more descriptive.
*   **`Base file`**: `data/entities/base_item_physics2.xml` - Inherits physics and item properties from a base entity.

### `PhysicsImageShapeComponent`

This component defines the visual and physical properties of the rocking chair.

*   **`image_file`**: `data/props_gfx/furniture_rocking_chair.png` - Specifies the sprite used for the rocking chair.
*   **`material`**: `wood_prop` - Defines the material type, which can influence interactions and physics.