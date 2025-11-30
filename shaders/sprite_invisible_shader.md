---
title: Sprite Invisible Shader
category: shaders
---

---

# Sprite Invisible Shader

This shader is used to render sprites, primarily for entities, with a focus on handling sprite atlases and applying a pixel-art friendly filtering effect. It allows for dynamic UV manipulation to select specific parts of a sprite atlas and blend in "stain" textures.

## Key Uniforms

These are the primary inputs that control the shader's behavior.

*   **`tex`**: The main sprite texture. This is typically a sprite atlas containing all the visual assets.
*   **`tex2`**: A reference texture used to determine UV coordinates for stains. It maps sprite regions to stain UVs.
*   **`tex3`**: The texture containing the "stain" or overlay graphics.
*   **`data`**: A `vec4` uniform containing:
    *   `data.xy`: Atlas scaling factors.
    *   `data.zw`: Atlas offset values.
*   **`tex_size`**: A `vec2` uniform representing the pixel dimensions of the `tex` texture.

## Pixel Art Filtering

The shader includes an optional `PIXEL_ART_FILTER` macro that, when enabled, applies a custom UV filtering technique.

### `pixel_art_filter_uv` Function

This function modifies the input UV coordinates to achieve a pixelated look, preventing blurring between virtual pixels.

*   **Purpose**: To simulate sharp pixel art rendering, especially when the game's texture filtering is set to bilinear.
*   **Mechanism**: It analyzes the fractional part of the UV coordinates and clamps them to create distinct pixel boundaries.
*   **`alpha`**: A constant (`vec2(0.08)`) that controls the smoothness of the transition between virtual pixels.

## Main Shader Logic (`main` function)

The `main` function orchestrates the sprite rendering process.

1.  **UV Calculation**:
    *   The primary sprite UV coordinates (`gl_TexCoord[0].xy`) are passed through the `pixel_art_filter_uv` function if the pixel art filter is enabled.
2.  **Stain UV Determination**:
    *   `texture2D(tex2, sprite_uv)` retrieves stain UV information from the reference texture.
    *   `stain_uv.xy *= data.xy;` and `stain_uv.xy += data.zw;` apply the atlas scaling and offset to position the stain correctly within its atlas.
3.  **Color Sampling**:
    *   `texture2D(tex, sprite_uv)` samples the main sprite color.
    *   `texture2D(tex3, stain_uv.xy)` samples the stain color.
4.  **Stain Blending**:
    *   `stain *= min(stain_uv_orig.y + 0.35, 1.0);` fades out the stain towards the top of the sprite.
    *   `mix(color.rgb, stain.rgb, min(stain.a * 1.5, 1.0))` blends the sprite color with the stain color based on the stain's alpha.
5.  **Final Color Output**:
    *   `out_color.a = (0.125 + stain.a) * color.a;` calculates the final alpha, incorporating a base value and the stain's alpha.
    *   `out_color *= gl_Color;` applies any vertex color modifiers.
    *   The final calculated `out_color` is assigned to `gl_FragColor`.

## Key Rendering Aspects

*   **Sprite Atlasing**: The shader is designed to work with sprite atlases, allowing efficient rendering of multiple sprites from a single texture.
*   **Stain/Overlay System**: It supports blending secondary textures (stains) onto the main sprite, with control over their position, scale, and alpha.
*   **Pixel Art Fidelity**: The optional pixel art filter ensures that sprites maintain a sharp, pixelated appearance.
*   **Alpha Blending**: The final output color's alpha is carefully calculated to manage transparency and layering.