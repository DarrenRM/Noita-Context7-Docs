---
title: Rock Statue 01
category: guides
---

<Entity name="unknown" >
  <Base file="data/entities/base_item_physics2.xml" >
    <PhysicsImageShapeComponent 
      image_file="data/props_gfx/statues/statue_rock_01.png"
      material="rock_box2d"
      >
    </PhysicsImageShapeComponent>
  </Base>
</Entity>
```

---
title: Rock Statue 01
category: entities
---

# Rock Statue 01

This document describes the `statue_rock_01.xml` entity, a basic rock statue prop in Noita.

## Entity Definition

The entity is defined as `unknown` and inherits from `data/entities/base_item_physics2.xml`.

### Key Components

*   **`PhysicsImageShapeComponent`**: This component defines the visual and physical properties of the statue.
    *   `image_file`: `data/props_gfx/statues/statue_rock_01.png` - Specifies the sprite used for the statue.
    *   `material`: `rock_box2d` - Assigns the physical material properties, likely affecting its interaction with physics (e.g., density, friction).

This is a simple prop entity primarily used for its visual representation and basic physics interactions. It does not appear to have any special behaviors or functionalities beyond what is provided by its base entity and physics component.