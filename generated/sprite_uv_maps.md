---
title: Sprite UV Maps
category: generated
---

# Sprite UV Maps

This section details auto-generated sprite UV map data. These maps are crucial for defining how textures are applied to sprites within the game engine.

## Purpose

Sprite UV maps provide the coordinates that map a portion of a texture image to a specific sprite. This allows for efficient use of texture atlases and precise control over sprite appearance.

## Key Attributes

While the exact attributes can vary, the core purpose of these files is to define the UV coordinates. Common elements you might encounter include:

*   **`sprite_id`**: A unique identifier for the sprite.
*   **`texture_path`**: The path to the texture file containing the sprite's image data.
*   **`uv_coords`**: A set of coordinates (typically `x1`, `y1`, `x2`, `y2`) that define the rectangular region within the texture that corresponds to the sprite. These are usually normalized values between 0 and 1.

## Usage in Modding

When creating or modifying sprites, understanding and potentially generating or editing these UV maps is essential. Mods that introduce new visual assets will likely need to define corresponding UV maps.

### Example (Conceptual)

```xml
<!-- This is a conceptual representation, actual files may differ -->
<SpriteUVMap id="my_new_sprite">
    <Texture path="textures/my_spritesheet.png"/>
    <UV x1="0.25" y1="0.5" x2="0.5" y2="0.75"/>
</SpriteUVMap>
```

This conceptual example shows how a sprite might be defined with its texture and its specific UV coordinates within that texture.