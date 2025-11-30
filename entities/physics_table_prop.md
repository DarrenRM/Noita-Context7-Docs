---
title: Physics Table Prop
category: entities
---

# Physics Table Prop

This document describes the `physics_table.xml` entity, which represents a basic physics-enabled table prop in Noita.

## Entity Definition

The core of this entity is its `Base` which inherits properties from `base_item_physics2.xml`. This indicates it's an item with physics properties.

```xml
<Entity name="unknown" >
  <Base file="data/entities/base_item_physics2.xml" >
    </Base>
</Entity>
```

## Key Components

### PhysicsImageShapeComponent

This component defines the visual representation and physical properties of the table.

*   **`image_file`**: Specifies the sprite used for the table.
    ```xml
    image_file="data/props_gfx/table.png"
    ```
*   **`material`**: Defines the physical material of the prop, influencing its interaction with other physics objects.
    ```xml
    material="wood_prop"
    ```