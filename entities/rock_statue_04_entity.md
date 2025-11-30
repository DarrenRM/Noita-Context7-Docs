---
title: Rock Statue 04 Entity
category: entities
---

# Rock Statue 04 Entity

This document describes the `statue_rock_04.xml` entity, a decorative rock statue for Noita.

## Entity Definition

The core of this entity is defined by its `name` and `Base` file.

```xml
<Entity name="unknown" >
  <Base file="data/entities/base_item_physics2.xml" >
    </Base>
</Entity>
```

*   **`name`**: "unknown" - This is a placeholder and likely intended to be more descriptive.
*   **`Base`**: `data/entities/base_item_physics2.xml` - Inherits physics and rendering properties from a generic physics item.

## Components

### PhysicsImageShapeComponent

This component defines the visual representation and physical properties of the statue.

```xml
    <PhysicsImageShapeComponent 
      image_file="data/props_gfx/statues/statue_rock_04.png"
      material="rock_box2d"
      >
    </PhysicsImageShapeComponent>
```

*   **`image_file`**: `data/props_gfx/statues/statue_rock_04.png` - Specifies the sprite used for the statue.
*   **`material`**: `rock_box2d` - Defines the physical material properties, influencing its interaction with the game world (e.g., how it breaks, its density).