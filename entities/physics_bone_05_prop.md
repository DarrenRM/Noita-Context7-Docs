---
title: Physics Bone 05 Prop
category: guides
---

<Entity name="unknown" >
  <Base file="data/entities/base_item_physics2.xml" >
    <PhysicsImageShapeComponent 
      image_file="data/props_gfx/bone_05.png"
      material="bone_box2d"
      >
    </PhysicsImageShapeComponent>
  </Base>
</Entity>
```

---
title: Physics Bone 05 Prop
category: entities
---

# Physics Bone 05 Prop

This document describes the `physics_bone_05.xml` entity, a simple physics-based prop in Noita.

## Entity Definition

The core of this entity is its inheritance from `base_item_physics2.xml`, indicating it's a physics-enabled item.

```xml
<Entity name="unknown" >
  <Base file="data/entities/base_item_physics2.xml" >
    <!-- Components go here -->
  </Base>
</Entity>
```

## Key Components

### PhysicsImageShapeComponent

This component defines the visual representation and physical properties of the prop.

| Attribute   | Value                 | Description                                     |
| :---------- | :-------------------- | :---------------------------------------------- |
| `image_file`| `data/props_gfx/bone_05.png` | Specifies the sprite used for the prop.       |
| `material`  | `bone_box2d`          | Defines the physics material and collision properties. |