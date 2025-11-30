---
title: Temple Rubble 06 Prop
category: entities
---

# Temple Rubble 06 Prop

This document describes the `physics_temple_rubble_06.xml` entity, a prop used in Noita. It represents a piece of rubble found in temple environments.

## Entity Definition

The entity is defined as `unknown` and inherits from `data/entities/base_item_physics2.xml`. This indicates it's a physics-enabled item.

## Key Components

### PhysicsBody2Component

This component governs the physical properties of the entity.

*   **`init_offset_y`**: `2.5` - An initial vertical offset applied to the physics body.

### PhysicsImageShapeComponent

This component defines the visual representation and collision shape of the entity.

*   **`image_file`**: `data/props_gfx/temple_rubble_06.png` - Specifies the image asset used for the rubble's appearance.
*   **`material`**: `rock_box2d` - Defines the physical material properties, influencing how it interacts with the game's physics engine.

```xml
<Entity name="unknown" >
	<Base file="data/entities/base_item_physics2.xml" >
		<PhysicsBody2Component
			init_offset_y="2.5"
			>
		</PhysicsBody2Component>
		<PhysicsImageShapeComponent 
			image_file="data/props_gfx/temple_rubble_06.png"
			material="rock_box2d"
			>
		</PhysicsImageShapeComponent>
	</Base>
</Entity>
```