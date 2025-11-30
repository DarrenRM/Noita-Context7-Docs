---
title: Cursor Pressure Plate Entity
category: entities
---

# Cursor Pressure Plate Entity

This document describes the `cursor_pressure_plate.xml` entity, which represents a pressure plate that can be activated by the player's cursor.

## Entity Definition

The core of the entity is defined by the `<Entity>` tag.

```xml
<Entity serialize="0">
    <!-- Components go here -->
</Entity>
```

*   `serialize="0"`: Indicates that this entity is not intended to be serialized (saved and loaded) in the game's save data.

## Key Components

### SpriteComponent

This component defines the visual representation of the pressure plate.

```xml
<SpriteComponent
    image_file="data/props_gfx/pressure_plate.xml"
    offset_x="12"
    offset_y="1" >
</SpriteComponent>
```

*   `image_file`: Specifies the XML file that contains the sprite definitions for the pressure plate. This allows for more complex visual setups than a simple image path.
*   `offset_x`, `offset_y`: These attributes define the pixel offset of the sprite from the entity's origin point. This is used for precise positioning.