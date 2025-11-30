---
title: Physics Bone 03 Prop
category: guides
---

<Entity name="physics_bone_03" >
  <Base file="data/entities/base_item_physics2.xml" >
    <PhysicsImageShapeComponent 
      image_file="data/props_gfx/bone_03.png"
      material="bone_box2d"
      >
    </PhysicsImageShapeComponent>
  </Base>
</Entity>
```

---
title: Physics Bone 03 Prop
category: entities
---

# Physics Bone 03 Prop

This entity defines a simple physics-enabled prop in Noita, specifically a bone. It inherits its core functionality from `base_item_physics2.xml`.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_physics2.xml"`**: This indicates that the entity inherits properties and behaviors from the base physics item definition. This likely includes general physics simulation, collision, and interaction capabilities.

### Physics Image Shape Component

*   **`PhysicsImageShapeComponent`**: This component defines the visual representation and physical shape of the prop.
    *   **`image_file="data/props_gfx/bone_03.png"`**: Specifies the graphical asset used for the bone's appearance.
    *   **`material="bone_box2d"`**: Defines the physical material properties of the bone, influencing its interaction with the physics engine (e.g., density, friction, bounciness). This material likely corresponds to a predefined set of physics parameters within Noita's engine.