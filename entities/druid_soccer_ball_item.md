---
title: Druid Soccer Ball Item
category: entities
---

# Druid Soccer Ball Item

This document describes the `druidsoccer_ball.xml` entity, which represents a special item in Noita.

## Entity Definition

The core of this item is defined by the `<Entity>` tag.

```xml
<Entity name="unknown" >
	<Base file="data/entities/base_item_physics.xml" >
    </Base>
</Entity>
```

This entity inherits its fundamental properties from `base_item_physics.xml`, indicating it's a physics-enabled item.

## Key Components

### PhysicsBodyComponent

This component governs the physical behavior of the item.

```xml
    <PhysicsBodyComponent 
      auto_clean="0" >
    </PhysicsBodyComponent>
```

*   **auto_clean**: Set to `0`, meaning the physics body will not be automatically removed when it becomes inactive.

### PhysicsImageShapeComponent

This component defines the visual representation and collision shape of the item.

```xml
    <PhysicsImageShapeComponent 
      image_file="data/items_gfx/easter/druidsoccer_ball.png"
      material="rock_box2d" >
    </PhysicsImageShapeComponent>
```

*   **image\_file**: Specifies the graphical asset used for the item: `data/items_gfx/easter/druidsoccer_ball.png`.
*   **material**: Defines the physics material for collision and interaction, set to `rock_box2d`.