---
title: Rock Statue 10
category: entities
---

# Rock Statue 10

This document describes the `statue_rock_10.xml` entity, representing a rock statue in Noita.

## Entity Definition

The core of this entity is defined by its `name` and its `Base` file, which inherits properties from `base_item_physics2.xml`.

```xml
<Entity name="unknown" >
  <Base file="data/entities/base_item_physics2.xml" >
    </Base>
</Entity>
```

## Key Components

### PhysicsImageShapeComponent

This component defines the visual representation and physical properties of the statue.

```xml
    <PhysicsImageShapeComponent 
      image_file="data/props_gfx/statues/statue_rock_10.png"
      material="rock_box2d"
      >
    </PhysicsImageShapeComponent>
```

*   **`image_file`**: Specifies the graphical asset used for the statue.
    *   `data/props_gfx/statues/statue_rock_10.png`
*   **`material`**: Defines the physical material properties, influencing its interaction with the game world (e.g., how it breaks, its density).
    *   `rock_box2d`