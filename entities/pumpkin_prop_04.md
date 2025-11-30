---
title: Pumpkin Prop (04)
category: entities
---

# Pumpkin Prop (04)

This document describes the `pumpkin_04.xml` entity, a decorative prop in Noita.

## Entity Definition

The core of this entity is defined by its `Base` file, inheriting properties from `data/entities/base_item_physics2.xml`. This indicates it's an item with physics-based behavior.

```xml
<Entity name="unknown" >
	<Base file="data/entities/base_item_physics2.xml" >
		<!-- ... components ... -->
	</Base>
</Entity>
```

## Key Components

### PhysicsImageShapeComponent

This component defines the visual representation and physical properties of the pumpkin.

*   **`image_file`**: Specifies the sprite used for the pumpkin.
    *   Value: `"data/props_gfx/pumpkin_04.png"`
*   **`material`**: Defines the physical material properties.
    *   Value: `"meat_pumpkin"`