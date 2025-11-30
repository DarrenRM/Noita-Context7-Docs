---
title: Furniture Tombstone 01
category: entities
---

# Furniture Tombstone 01

This document describes the `furniture_tombstone_01.xml` entity, representing a decorative tombstone prop in Noita.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag.

```xml
<Entity name="unknown" >
	<Base file="data/entities/base_item_physics2.xml" >
		<PhysicsImageShapeComponent 
			image_file="data/props_gfx/furniture_tombstone_01.png"
			material="rock_box2d"
			>
		</PhysicsImageShapeComponent>
	</Base>
</Entity>
```

## Key Components and Attributes

### Base Entity

*   **`<Base file="data/entities/base_item_physics2.xml">`**: This indicates that the tombstone inherits its fundamental physics and interaction properties from `base_item_physics2.xml`. This is a common base for many physical objects in Noita.

### Physics Image Shape Component

*   **`<PhysicsImageShapeComponent>`**: This component defines the visual representation and physical shape of the entity.
    *   **`image_file="data/props_gfx/furniture_tombstone_01.png"`**: Specifies the graphical asset used for the tombstone's appearance.
    *   **`material="rock_box2d"`**: Assigns a physics material to the tombstone. `rock_box2d` suggests it behaves like a solid, rocky object within the game's physics engine.

## Summary

The `furniture_tombstone_01.xml` entity is a simple prop that utilizes a base physics entity and defines its visual appearance and physical properties through the `PhysicsImageShapeComponent`. It's designed to be a static, rock-like object within the game world.