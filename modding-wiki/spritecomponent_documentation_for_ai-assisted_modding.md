---
title: SpriteComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:SpriteComponent
category: modding-wiki
---

# SpriteComponent Documentation

This document details the `SpriteComponent` in Noita, a crucial component for defining and managing visual elements within the game. Understanding `SpriteComponent` is essential for modders looking to add new sprites, modify existing ones, and control how they are displayed, animated, and interacted with in their mods.

## Overview of SpriteComponent

The `SpriteComponent` is responsible for all visual aspects of an entity that are rendered as a sprite. This includes the sprite's image, its animation frames, its position relative to the entity, and various visual effects. Modders will frequently interact with this component when creating new entities, adding visual flair to existing ones, or implementing custom animations.

## Core Functionality and Properties

The `SpriteComponent` has several key properties that control its behavior. These are typically defined within an entity's XML definition.

### Basic Sprite Properties

*   **_tags**: A comma-separated list of tags associated with the sprite. These can be used for identification and manipulation in Lua scripts.
*   **_enabled**: A boolean value (0 or 1) that determines if the sprite is currently visible and active.
*   **_child_id**: The ID of a child entity that this sprite is attached to.
*   **_parent_id**: The ID of the parent entity that this sprite belongs to.
*   **_sprite_file**: The path to the sprite image file (e.g., `data/sprites/my_sprite.png`).
*   **_sprite_name**: The name of the specific sprite within the sprite file to use. This is often used when a single file contains multiple sprites.
*   **_sprite_width**: The width of the sprite in pixels.
*   **_sprite_height**: The height of the sprite in pixels.
*   **_sprite_offset_x**: The horizontal offset of the sprite from the entity's origin.
*   **_sprite_offset_y**: The vertical offset of the sprite from the entity's origin.
*   **_sprite_flip_x**: A boolean value (0 or 1) to flip the sprite horizontally.
*   **_sprite_flip_y**: A boolean value (0 or 1) to flip the sprite vertically.
*   **_sprite_rotation**: The rotation of the sprite in degrees.
*   **_sprite_scale_x**: The horizontal scaling factor for the sprite.
*   **_sprite_scale_y**: The vertical scaling factor for the sprite.
*   **_sprite_material**: The material applied to the sprite, affecting its rendering properties (e.g., `data/materials.xml`).
*   **_sprite_render_order**: The order in which the sprite is rendered relative to other sprites. Higher values are rendered on top.
*   **_sprite_color_r**, **_sprite_color_g**, **_sprite_color_b**, **_sprite_color_a**: RGBA color values (0-255) to tint the sprite.

### Animation Properties

If the sprite is animated, the following properties are relevant:

*   **_animation_speed**: The speed of the animation in frames per second.
*   **_animation_loop**: A boolean value (0 or 1) indicating whether the animation should loop.
*   **_animation_frame_count**: The total number of frames in the animation.
*   **_animation_frame_width**: The width of a single animation frame.
*   **_animation_frame_height**: The height of a single animation frame.
*   **_animation_frame_offset_x**: The horizontal offset for each animation frame.
*   **_animation_frame_offset_y**: The vertical offset for each animation frame.
*   **_animation_frames_per_row**: The number of frames in each row of the sprite sheet.
*   **_animation_frames_per_column**: The number of frames in each column of the sprite sheet.
*   **_animation_start_frame**: The index of the frame to start the animation from.
*   **_animation_end_frame**: The index of the frame to end the animation on.

### Example XML Definition

Here's a simplified example of how a `SpriteComponent` might be defined in an entity's XML file:

```xml
<Entity name="my_animated_object">
    <SpriteComponent
        _tags="animated,visual"
        _enabled="1"
        _sprite_file="data/sprites/animated_thing.png"
        _sprite_name="idle"
        _sprite_width="32"
        _sprite_height="32"
        _animation_speed="10"
        _animation_loop="1"
        _animation_frame_count="8"
        _animation_frames_per_row="8"
        _animation_frames_per_column="1"
        _animation_frame_width="32"
        _animation_frame_height="32"
    />
    <!-- Other components -->
</Entity>
```

## Modifying SpriteComponent with Lua

While many properties can be set directly in XML, modders often use Lua scripting to dynamically control `SpriteComponent` properties, especially for animations, visual effects, and conditional rendering.

### Accessing SpriteComponent in Lua

You can access the `SpriteComponent` of an entity using its `GetComponent` method.

```lua
local entity = GetEntityByName("my_animated_object")
if entity then
    local sprite_component = entity:GetComponent("SpriteComponent")
    if sprite_component then
        -- Now you can manipulate sprite_component properties
    end
end
```

### Common Lua Manipulations

*   **Changing the sprite:**
    ```lua
    sprite_component:SetSpriteName("walking")
    ```

*   **Enabling/Disabling the sprite:**
    ```lua
    sprite_component:SetEnabled(false) -- or true
    ```

*   **Modifying animation speed:**
    ```lua
    sprite_component:SetAnimationSpeed(15)
    ```

*   **Changing sprite color:**
    ```lua
    sprite_component:SetColor(255, 0, 0, 255) -- Red tint
    ```

*   **Flipping the sprite:**
    ```lua
    sprite_component:SetFlipX(true)
    ```

### Lua API References

For a comprehensive list of available Lua functions for `SpriteComponent` and other components, refer to the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API).

## Sprite Sheets and Animation

Noita commonly uses sprite sheets for animations. A sprite sheet is a single image file containing multiple frames of an animation arranged in a grid. The `SpriteComponent` properties related to animation (e.g., `_animation_frames_per_row`, `_animation_frame_width`) are crucial for correctly interpreting these sheets.

### Example Sprite Sheet Structure

Imagine a sprite sheet named `data/sprites/player_walk.png` that contains 8 frames of a walking animation, arranged in a single row.

*   `_sprite_file`: `data/sprites/player_walk.png`
*   `_animation_frame_count`: 8
*   `_animation_frames_per_row`: 8
*   `_animation_frames_per_column`: 1
*   `_animation_frame_width`: 16 (if each frame is 16 pixels wide)
*   `_animation_frame_height`: 16 (if each frame is 16 pixels high)

The `_sprite_name` would typically refer to the overall animation, and the component would cycle through the frames based on the animation properties.

## Important Considerations for Modding

*   **File Paths**: Ensure all sprite file paths are correct and relative to the `data` directory.
*   **Sprite Naming Conventions**: Consistent naming of sprites within a file (e.g., `idle`, `walk`, `attack`) makes them easier to manage in Lua.
*   **Performance**: While not a primary concern for simple sprite changes, excessively large sprite sheets or complex animations can impact performance.
*   **Compatibility**: Be mindful of how your sprite changes might interact with other mods that also modify the same entities or components.

By mastering the `SpriteComponent`, modders can significantly enhance the visual appeal and interactivity of their Noita mods, bringing new life and unique aesthetics to the game.