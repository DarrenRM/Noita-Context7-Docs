---
title: Physics Skull 01 Prop
category: guides
---

<Entity name="physics_skull_01" >
  <Base file="data/entities/base_item_physics2.xml" >
    <PhysicsImageShapeComponent 
      image_file="data/props_gfx/skull_01.png"
      material="bone_box2d"
      >
    </PhysicsImageShapeComponent>
  </Base>
</Entity>
```

---
title: Physics Skull 01 Prop
category: entities
---

# Physics Skull 01 Prop

This entity represents a physics-enabled skull prop in Noita. It inherits its base functionality from `base_item_physics2.xml`.

## Key Components and Attributes

### Base Entity

*   **`name`**: `physics_skull_01` - The unique identifier for this entity.
*   **`Base file`**: `data/entities/base_item_physics2.xml` - Inherits physics and item-related properties.

### Physics Image Shape Component

This component defines the visual representation and physical properties of the skull.

*   **`image_file`**: `data/props_gfx/skull_01.png` - Specifies the sprite used for the skull's appearance.
*   **`material`**: `bone_box2d` - Defines the physical material properties, influencing how it interacts with the physics engine (e.g., friction, density).