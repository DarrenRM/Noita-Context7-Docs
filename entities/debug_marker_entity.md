---
title: Debug Marker Entity
category: entities
---

# Debug Marker Entity

This entity is a simple visual marker used for debugging purposes in Noita. It displays a sprite and emits a small light.

## Key Components

### SpriteComponent

This component defines the visual appearance of the debug marker.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `_enabled`  | Whether the sprite is active (1 for enabled).   |
| `alpha`     | Transparency of the sprite (1 is fully opaque). |
| `offset_x`  | Horizontal offset of the sprite.                |
| `offset_y`  | Vertical offset of the sprite.                  |
| `image_file`| Path to the sprite image file.                  |

### LightComponent

This component adds a light source to the debug marker.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `_enabled`| Whether the light is active (1 for enabled).|
| `radius`  | The radius of the light's illumination.   |