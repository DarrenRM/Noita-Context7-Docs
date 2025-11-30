---
title: Wooden Board 08 Entity
category: entities
---

# Wooden Board 08 Entity

This document describes the `wooden_board08.xml` entity, a simple building element in Noita.

## Entity Definition

The core of the entity is defined by the `<Entity>` tag.

```xml
<Entity serialize="0">
    <!-- Components go here -->
</Entity>
```

- `serialize="0"`: Indicates that this entity is not intended to be serialized (saved/loaded) in its current state.

## Components

This entity utilizes the following components:

### SpriteComponent

This component handles the visual representation of the entity.

```xml
<SpriteComponent 
    image_file="data/temp/building/wooden_board08.xml" >
</SpriteComponent>
```

- `image_file`: Specifies the path to the sprite image used for this entity. In this case, it points to `data/temp/building/wooden_board08.xml`, which likely contains the actual sprite data or a reference to it.

### SpriteComponent (Blit Target)

A second `SpriteComponent` is present, tagged for blitting.

```xml
<SpriteComponent 
    _tags="blit_target"
    update_transform="0"
    update_transform_rotation="0" >
</SpriteComponent>
```

- `_tags="blit_target"`: This tag suggests that this sprite is intended to be rendered as part of a blitting operation, often used for optimizing rendering of static or background elements.
- `update_transform="0"`: Disables automatic updating of the sprite's transform (position, scale, rotation) based on its parent entity.
- `update_transform_rotation="0"`: Specifically disables automatic updating of the sprite's rotation.

This configuration implies that the `wooden_board08` entity is a static visual element with no dynamic movement or rotation applied through its components.