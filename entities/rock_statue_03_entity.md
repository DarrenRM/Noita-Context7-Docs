---
title: Rock Statue 03 Entity
category: guides
---

<Entity name="unknown" >
  <Base file="data/entities/base_item_physics2.xml" >
    <PhysicsImageShapeComponent 
      image_file="data/props_gfx/statues/statue_rock_03.png"
      material="rock_box2d"
      >
    </PhysicsImageShapeComponent>
  </Base>
</Entity>
```

---
title: Rock Statue 03 Entity
category: entities
---

# Rock Statue 03 Entity

This document describes the `statue_rock_03.xml` entity, a decorative rock statue prop in Noita.

## Key Attributes

The primary function of this entity is to act as a static, physics-enabled prop.

### `Entity`

*   **name**: `unknown` (This is a placeholder and likely intended to be more descriptive in a modded context.)

### `Base`

*   **file**: `data/entities/base_item_physics2.xml`
    *   This indicates the entity inherits physics properties and behaviors from the `base_item_physics2.xml` template, suggesting it can be interacted with physically (e.g., pushed, broken).

### `PhysicsImageShapeComponent`

*   **image_file**: `data/props_gfx/statues/statue_rock_03.png`
    *   Specifies the graphical asset used for the statue's appearance.
*   **material**: `rock_box2d`
    *   Defines the physical material properties of the statue, influencing its interaction with the game's physics engine (e.g., density, friction).