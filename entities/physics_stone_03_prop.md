---
title: Physics Stone 03 Prop
category: guides
---

<Entity name="unknown" >
  <Base file="data/entities/base_item_physics2.xml" >
    <PhysicsImageShapeComponent 
      image_file="data/props_gfx/stone_03.png"
      material="rock_box2d"
      >
    </PhysicsImageShapeComponent>
  </Base>
</Entity>
```

---
title: Physics Stone 03 Prop
category: entities
---

# Physics Stone 03 Prop

This entity defines a basic physics-based prop, specifically a stone object. It inherits its core functionality from `base_item_physics2.xml`.

## Key Components and Attributes

### Base Entity

*   **`Base file="data/entities/base_item_physics2.xml"`**: Inherits fundamental physics and item properties.

### Physics Image Shape Component

*   **`PhysicsImageShapeComponent`**: This component handles the visual representation and physical collision of the prop.
    *   **`image_file="data/props_gfx/stone_03.png"`**: Specifies the graphical asset used for the stone's appearance.
    *   **`material="rock_box2d"`**: Defines the physical material properties, influencing how it interacts with the physics engine (e.g., friction, density). This likely corresponds to a predefined material in Noita's physics system.