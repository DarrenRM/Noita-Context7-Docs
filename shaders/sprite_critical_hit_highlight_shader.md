---
title: Sprite Critical Hit Highlight Shader
category: shaders
---

# Sprite Critical Hit Highlight Shader

This shader is designed to apply a visual highlight to sprites, specifically intended for critical hit effects in Noita. It modifies the fragment color to render a bright red, while preserving the original alpha channel of the sprite.

## Key Functionality

### `pixel_art_filter_uv` Function

This function is responsible for generating texture coordinates that are friendly to pixel art rendering. It aims to create sharp edges between virtual pixels, preventing unwanted blurring.

*   **Purpose:** To ensure pixelated textures maintain their crisp appearance, even with bilinear filtering enabled.
*   **Mechanism:** It manipulates UV coordinates based on a small `alpha` value to create a smooth transition zone between virtual pixels.
*   **Conditional Compilation:** The `#ifdef PIXEL_ART_FILTER` directive allows this functionality to be enabled or disabled. If disabled, it simply returns the original UV coordinates.

### `main` Function

The core of the shader, executed for each fragment (pixel) of the sprite.

*   **Texture Sampling:** It samples the texture using the `tex` uniform and the potentially filtered UV coordinates from `pixel_art_filter_uv`.
*   **Color Output:** The `gl_FragColor` is set to a bright red (`vec4( 1.0, 0.0, 0.0, color.a )`). This means the sprite will be rendered as red, but its transparency (alpha channel) from the original texture will be maintained.

## Uniforms

*   `tex`: A `sampler2D` uniform representing the texture to be rendered.
*   `tex_size`: A `vec2` uniform representing the dimensions of the texture in pixels.

## Preprocessor Directives

*   `#version 110`: Specifies the GLSL version.
*   `#define PIXEL_ART_FILTER`: Enables the pixel art filtering logic.

## Example Usage (Conceptual)

This shader would typically be applied to a sprite that needs to flash or glow when a critical hit occurs. The red color serves as a clear visual indicator of this event.

```lua
-- Example of how this shader might be applied in Noita's Lua scripting
-- (This is a conceptual example and not actual Noita API code)

local sprite_entity = create_sprite_entity()
local shader_component = create_shader_component("data/shaders/sprite_damage_critical_hit_highlight.frag")
add_component(sprite_entity, shader_component)

-- When a critical hit occurs:
function on_critical_hit(target_entity)
    -- Apply the highlight shader to the target's sprite
    local sprite = get_component(target_entity, "sprite")
    if sprite then
        set_shader(sprite, "data/shaders/sprite_damage_critical_hit_highlight.frag")
        -- Potentially trigger a timer to revert the shader
    end
end
```