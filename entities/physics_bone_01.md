---
title: Physics Bone 01
category: entities
---

---

# Physics Bone 01

This document describes the `physics_bone_01.xml` entity, a basic physics-based prop in Noita.

## Entity Definition

The entity is named "unknown" and inherits its base properties from `base_item_physics2.xml`.

```xml
<Entity name="unknown">
	<Base file="data/entities/base_item_physics2.xml">
		<!-- ... -->
	</Base>
</Entity>
```

## Key Components

### PhysicsImageShapeComponent

This component defines the visual representation and physical properties of the bone prop.

*   **`image_file`**: Specifies the sprite used for the bone.
    *   Value: `"data/props_gfx/bone_01.png"`
*   **`material`**: Defines the physical material properties for collision and interaction.
    *   Value: `"bone_box2d"`

```xml
<PhysicsImageShapeComponent
	image_file="data/props_gfx/bone_01.png"
	material="bone_box2d">
</PhysicsImageShapeComponent>