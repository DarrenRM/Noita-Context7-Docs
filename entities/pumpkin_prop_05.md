---
title: Pumpkin Prop (05)
category: entities
---

# Pumpkin Prop (05)

This document describes the `pumpkin_05.xml` entity, a decorative prop in Noita.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag.

```xml
<Entity name="unknown" >
	<Base file="data/entities/base_item_physics2.xml" >
		<PhysicsImageShapeComponent 
			image_file="data/props_gfx/pumpkin_05.png"
			material="meat_pumpkin"
			>
		</PhysicsImageShapeComponent>
	</Base>
</Entity>
```

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_physics2.xml"`**: This indicates that the pumpkin prop inherits properties and behaviors from the `base_item_physics2.xml` entity. This likely provides it with physics-based interactions and visual representation.

### Physics Image Shape Component

*   **`PhysicsImageShapeComponent`**: This component defines the visual appearance and physical properties of the prop.
    *   **`image_file="data/props_gfx/pumpkin_05.png"`**: Specifies the image file used for the pumpkin's graphics.
    *   **`material="meat_pumpkin"`**: Assigns a material to the pumpkin. This material likely dictates its physical properties, such as how it interacts with other objects, its durability, and potentially its behavior when damaged or destroyed.