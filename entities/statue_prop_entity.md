---
title: Statue Prop Entity
category: entities
---

# Statue Prop Entity

This document describes the `statue.xml` entity, which defines a basic prop entity in Noita.

## Entity Definition

The `statue.xml` entity is a simple prop with physics and sprite components.

```xml
<Entity tags="prop" >
    <VelocityComponent />
    <SimplePhysicsComponent/>
    <SpriteComponent 
        z_index="1"
        image_file="data/props_gfx/statue.xml" 
        offset_x="0"
        offset_y="0" >
    </SpriteComponent>
</Entity>
```

## Key Components and Attributes

### VelocityComponent

This component is present but has no specific attributes defined in this example. It typically handles the entity's velocity and movement.

### SimplePhysicsComponent

This component enables basic physics interactions for the entity. No specific attributes are defined here, meaning it will use default physics properties.

### SpriteComponent

This component defines the visual representation of the statue.

*   **`z_index`**: `1` - Determines the rendering order. A higher `z_index` means it will be drawn on top of other elements with lower `z_index`.
*   **`image_file`**: `"data/props_gfx/statue.xml"` - Specifies the path to the sprite's graphical data.
*   **`offset_x`**: `0` - Horizontal offset for the sprite.
*   **`offset_y`**: `0` - Vertical offset for the sprite.