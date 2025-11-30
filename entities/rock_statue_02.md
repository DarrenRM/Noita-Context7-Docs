---
title: Rock Statue 02
category: entities
---

# Rock Statue 02

This document describes the `statue_rock_02.xml` entity, a decorative rock statue found in Noita.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag.

```xml
<Entity name="unknown" >
  <Base file="data/entities/base_item_physics2.xml" >
    <PhysicsImageShapeComponent 
      image_file="data/props_gfx/statues/statue_rock_02.png"
      material="rock_box2d"
      >
    </PhysicsImageShapeComponent>
  </Base>
</Entity>
```

## Key Components

### Base Entity

*   **`<Base file="data/entities/base_item_physics2.xml">`**: This indicates that the statue inherits its fundamental physics and item properties from `base_item_physics2.xml`. This means it will behave like a physical object that can be interacted with in the game world.

### Physics Image Shape Component

*   **`<PhysicsImageShapeComponent>`**: This component defines the visual representation and physical collision shape of the entity.
    *   **`image_file="data/props_gfx/statues/statue_rock_02.png"`**: Specifies the image file used for the statue's sprite.
    *   **`material="rock_box2d"`**: Defines the physical material properties of the statue, likely influencing its collision behavior and how it interacts with other game elements (e.g., it's a solid, non-flammable rock).