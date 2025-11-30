---
title: Rock Statue 07
category: entities
---

# Rock Statue 07

This document describes the `statue_rock_07.xml` entity, a decorative rock statue found in Noita.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag.

```xml
<Entity name="unknown" >
  <Base file="data/entities/base_item_physics2.xml" >
    <PhysicsImageShapeComponent 
      image_file="data/props_gfx/statues/statue_rock_07.png"
      material="rock_box2d"
      >
    </PhysicsImageShapeComponent>
  </Base>
</Entity>
```

## Key Components

### Base Entity

*   **`<Base file="data/entities/base_item_physics2.xml">`**: This indicates that the statue inherits properties from the `base_item_physics2.xml` entity. This likely provides it with basic physics, collision, and visual rendering capabilities.

### Physics and Graphics

*   **`<PhysicsImageShapeComponent>`**: This component defines the physical shape and visual representation of the entity.
    *   **`image_file="data/props_gfx/statues/statue_rock_07.png"`**: Specifies the image file used for the statue's appearance.
    *   **`material="rock_box2d"`**: Assigns a physics material to the statue, likely influencing its interaction with the game world (e.g., how it collides, its density).