---
title: Wooden Chair Prop
category: guides
---

<Entity name="unknown" >
	<Base file="data/entities/base_item_physics2.xml" >
		<PhysicsImageShapeComponent 
			image_file="data/props_gfx/furniture_wood_chair.png"
			material="wood_prop"
			>
		</PhysicsImageShapeComponent>
	</Base>
</Entity>
```

---
title: Wooden Chair Prop
category: entities
---

# Wooden Chair Prop

This document describes the `furniture_wood_chair.xml` entity, which represents a basic wooden chair prop in Noita.

## Entity Definition

The core of this entity is its inheritance from `base_item_physics2.xml`, indicating it's a physics-enabled item.

```xml
<Entity name="unknown" >
	<Base file="data/entities/base_item_physics2.xml" >
		<!-- ... components ... -->
	</Base>
</Entity>
```

## Key Components

### PhysicsImageShapeComponent

This component defines the visual representation and physical properties of the chair.

| Attribute   | Value                               | Description                                                                 |
| :---------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `image_file`| `data/props_gfx/furniture_wood_chair.png` | Specifies the sprite used for the chair.                                    |
| `material`  | `wood_prop`                         | Defines the material type, influencing its physical interactions and properties. |