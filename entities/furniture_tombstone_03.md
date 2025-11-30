---
title: Furniture Tombstone 03
category: entities
---

---

# Furniture Tombstone 03

This document describes the `furniture_tombstone_03.xml` entity, a decorative tombstone prop in Noita.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag.

```xml
<Entity name="unknown" >
	<Base file="data/entities/base_item_physics2.xml" >
		<PhysicsImageShapeComponent 
			image_file="data/props_gfx/furniture_tombstone_03.png"
			material="rock_box2d"
			>
		</PhysicsImageShapeComponent>
	</Base>
</Entity>
```

## Key Components and Attributes

### Base Entity

*   **`<Base file="data/entities/base_item_physics2.xml">`**: This indicates that the tombstone inherits properties from the `base_item_physics2.xml` entity. This likely provides it with physics-related behaviors, such as collision and gravity.

### Physics Image Shape Component

*   **`<PhysicsImageShapeComponent>`**: This component defines the visual representation and physical shape of the entity.
    *   **`image_file="data/props_gfx/furniture_tombstone_03.png"`**: Specifies the image file used for the tombstone's graphics.
    *   **`material="rock_box2d"`**: Assigns a material property to the entity, likely influencing its interaction with physics and other game elements. This suggests it behaves like a solid, rocky object.

## Summary

The `furniture_tombstone_03.xml` entity is a simple prop that utilizes a base physics entity and a visual component to represent a tombstone. Its primary function is decorative, with its physical properties defined by the `rock_box2d` material.