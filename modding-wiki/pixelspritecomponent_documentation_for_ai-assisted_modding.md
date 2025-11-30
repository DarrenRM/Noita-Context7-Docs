---
title: PixelSpriteComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:PixelSpriteComponent
category: modding-wiki
---

# PixelSpriteComponent Documentation

This documentation covers the `PixelSpriteComponent` in Noita, a crucial component for defining and managing visual sprites within the game. Understanding this component is essential for modders looking to create custom visual elements, modify existing sprites, and control how they are rendered, impacting everything from character appearances to environmental details.

## Overview of PixelSpriteComponent

The `PixelSpriteComponent` is responsible for handling the visual representation of entities in Noita. It dictates which sprite is used, its color, animation, and other visual properties. This component is fundamental for any mod that aims to introduce new visual assets or alter the appearance of existing ones.

## Component Properties

The `PixelSpriteComponent` has several properties that can be configured in `.xml` files. These properties allow for fine-grained control over the sprite's appearance and behavior.

### Core Properties

| Property Name | Type | Description | Default Value |
|---|---|---|---|
| `_enabled` | boolean | Whether the component is active. | `true` |
| `sprite_file` | string | The path to the sprite's `.png` file. | `""` |
| `sprite_id` | string | The ID of the sprite within the sprite file. | `""` |
| `sprite_frame` | integer | The specific frame of an animated sprite to display. | `0` |
| `sprite_offset_x` | float | Horizontal offset for the sprite. | `0` |
| `sprite_offset_y` | float | Vertical offset for the sprite. | `0` |
| `sprite_scale_x` | float | Horizontal scaling factor for the sprite. | `1` |
| `sprite_scale_y` | float | Vertical scaling factor for the sprite. | `1` |
| `sprite_rotation` | float | Rotation angle of the sprite in degrees. | `0` |
| `sprite_flip_x` | boolean | Whether to flip the sprite horizontally. | `false` |
| `sprite_flip_y` | boolean | Whether to flip the sprite vertically. | `false` |
| `sprite_color_r` | float | Red component of the sprite's color (0.0 to 1.0). | `1` |
| `sprite_color_g` | float | Green component of the sprite's color (0.0 to 1.0). | `1` |
| `sprite_color_b` | float | Blue component of the sprite's color (0.0 to 1.0). | `1` |
| `sprite_color_a` | float | Alpha (transparency) component of the sprite's color (0.0 to 1.0). | `1` |

### Animation Properties

When using animated sprites, additional properties become relevant:

| Property Name | Type | Description | Default Value |
|---|---|---|---|
| `animation_speed` | float | Speed at which the animation plays. | `1` |
| `animation_loop` | boolean | Whether the animation should loop. | `true` |
| `animation_start_frame` | integer | The frame to start the animation from. | `0` |
| `animation_end_frame` | integer | The frame to end the animation on. | `-1` (plays to the end of the sprite's frames) |

## Example Usage in XML

Here's an example of how to define a `PixelSpriteComponent` in an entity's `.xml` file:

```xml
<Entity name="my_custom_sprite_entity">
    <PixelSpriteComponent
        sprite_file="data/sprites/my_custom_sprite.png"
        sprite_id="my_sprite_id"
        sprite_offset_x="5"
        sprite_offset_y="-10"
        sprite_color_r="0.8"
        sprite_color_g="0.2"
        sprite_color_b="0.2"
        sprite_flip_x="true"
    />
    <!-- Other components -->
</Entity>
```

This example defines an entity with a custom sprite, offset, a reddish tint, and horizontally flipped.

## Working with Sprite Files and IDs

Sprites in Noita are typically defined in `.png` files and referenced by a `sprite_id` within those files.

### Sprite File Structure

Sprite files often contain multiple frames for animations or different variations of a sprite. The `sprite_id` helps to select a specific part of this sprite sheet.

### Finding Sprite IDs

You can often find existing `sprite_id`s by examining the game's default `.xml` files or by using modding tools that can inspect game assets.

## Lua Integration

While `PixelSpriteComponent` is primarily configured via XML, its properties can be dynamically modified or controlled using Lua scripting.

### Accessing the Component

You can get a reference to the `PixelSpriteComponent` of an entity using Lua:

```lua
local entity_id = GetUpdatedGameLua(self) -- Assuming 'self' is the entity object
local pixel_sprite_comp = EntityGetFirstComponent(entity_id, "PixelSpriteComponent")

if pixel_sprite_comp then
    -- Access and modify properties
    ComponentSetValue(pixel_sprite_comp, "sprite_color_a", 0.5) -- Make sprite semi-transparent
end
```

### Modifying Sprite Properties via Lua

You can change various properties of the `PixelSpriteComponent` at runtime:

```lua
-- Example: Changing the sprite frame
local new_frame = 5
ComponentSetValue(pixel_sprite_comp, "sprite_frame", new_frame)

-- Example: Flipping the sprite
local current_flip_x = ComponentGetValue(pixel_sprite_comp, "sprite_flip_x")
ComponentSetValue(pixel_sprite_comp, "sprite_flip_x", not current_flip_x)
```

## Important Links

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Entity XML Documentation](https://noita.wiki.gg/wiki/Modding:_Entity_XML_Documentation)