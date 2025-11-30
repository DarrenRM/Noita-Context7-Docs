---
title: Pumpkin Prop (pumpkin_01)
category: guides
---

<Entity name="pumpkin_01" >
	<Base file="data/entities/base_item_physics2.xml" >
		<PhysicsImageShapeComponent 
			image_file="data/props_gfx/pumpkin_01.png"
			material="meat_pumpkin"
			>
		</PhysicsImageShapeComponent>
	</Base>
</Entity>
```

---
title: Pumpkin Prop (pumpkin_01)
category: entities
---

# Pumpkin Prop (pumpkin_01)

This document describes the `pumpkin_01` entity, a simple prop in Noita.

## Key Attributes

*   **`name`**: `pumpkin_01` - The unique identifier for this entity.
*   **`Base file`**: `data/entities/base_item_physics2.xml` - Inherits physics and item properties from a base entity.

### `PhysicsImageShapeComponent`

This component defines the visual representation and physical properties of the pumpkin.

*   **`image_file`**: `data/props_gfx/pumpkin_01.png` - Specifies the graphical asset used for the pumpkin's appearance.
*   **`material`**: `meat_pumpkin` - Defines the material properties, likely influencing its interaction with other game elements (e.g., damage, physics).