---
title: Wooden Board Entity
category: entities
---

# Wooden Board Entity

This document describes the `wooden_board16.xml` entity, representing a wooden board in Noita.

## Entity Definition

The core of the entity is defined by the `<Entity>` tag.

```xml
<Entity serialize="0">
    <!-- Components go here -->
</Entity>
```

## Key Components

### SpriteComponent

This component defines the visual representation of the wooden board.

*   **`image_file`**: Specifies the image file used for the sprite.
    *   `data/temp/building/wooden_board16.xml`

There are two `SpriteComponent` instances. The first defines the primary image. The second, with `_tags="blit_target"`, likely handles rendering or layering without updating its transform, ensuring it stays in place.

```xml
<SpriteComponent 
    image_file="data/temp/building/wooden_board16.xml" >
</SpriteComponent>

<SpriteComponent 
    _tags="blit_target"
    update_transform="0"
    update_transform_rotation="0" >
</SpriteComponent>
```