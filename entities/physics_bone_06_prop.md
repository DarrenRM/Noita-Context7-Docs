---
title: Physics Bone 06 Prop
category: entities
---

# Physics Bone 06 Prop

This document describes the `physics_bone_06.xml` entity, which represents a physics-enabled prop in Noita.

## Entity Definition

The core of this entity is its `Base` which inherits properties from `base_item_physics2.xml`. This indicates it's a physics-based item with standard physics interactions.

```xml
<Entity name="unknown" >
  <Base file="data/entities/base_item_physics2.xml" >
    </Base>
</Entity>
```

## Physics Image Shape Component

This component defines the visual representation and physical properties of the prop.

### Key Attributes

*   **`image_file`**: Specifies the graphical asset used for the prop.
    *   Value: `"data/props_gfx/bone_06.png"`
*   **`material`**: Defines the physical material properties, influencing how it interacts with the game world (e.g., friction, density).
    *   Value: `"bone_box2d"`

```xml
    <PhysicsImageShapeComponent
      image_file="data/props_gfx/bone_06.png"
      material="bone_box2d"
      >
    </PhysicsImageShapeComponent>
```