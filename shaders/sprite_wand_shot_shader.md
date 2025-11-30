---
title: Sprite Wand Shot Shader
category: shaders
---

# Sprite Wand Shot Shader

This shader is responsible for rendering the visual effect of projectiles fired from wands in Noita. It applies a highlight effect and handles pixel art-style texture filtering.

## Key Uniforms

These are the primary variables that can be adjusted to modify the shader's behavior.

| Uniform Name | Type | Description |
|---|---|---|
| `tex` | `sampler2D` | The texture containing the sprite for the wand shot. |
| `data` | `vec4` | Controls the highlight color and intensity. `data.rgb` is the highlight color, and `data.a` might influence intensity or other properties. |
| `tex_size` | `vec2` | The dimensions of the `tex` texture in pixels. |

## Pixel Art Filtering

The shader includes an optional `PIXEL_ART_FILTER` that aims to create a sharper, pixelated look, even when the game's texture filtering is set to bilinear.

### `pixel_art_filter_uv` Function

This function takes a UV coordinate and the texture size and returns a modified UV coordinate suitable for pixel art rendering.

*   **`alpha`**: A constant (`0.08`) that controls the size of the smooth transition between virtual pixels. Smaller values result in sharper edges.
*   **Logic**: The function manipulates the UV coordinates to snap them to the center of virtual pixels, creating a pixelated appearance.

## Main Shader Logic

The `main` function orchestrates the rendering process.

### Constants

| Constant Name | Value | Description |
|---|---|---|
| `HIGHLIGHT_SIZE` | `1.0` | Controls the overall size of the highlight effect. |
| `HIGHLIGHT_ALPHA` | `0.8` | Controls the transparency/intensity of the highlight. |
| `p` | `0.15` | A positional offset used in the highlight calculation, likely related to the sprite's horizontal center. |

### Rendering Steps

1.  **UV Calculation**: The `gl_TexCoord[0].xy` (the sprite's UV coordinates) are passed through the `pixel_art_filter_uv` function to get filtered UVs.
2.  **Texture Sampling**: The `tex` (sprite texture) is sampled using the filtered UVs to get the base `color`.
3.  **Highlight Application**:
    *   A highlight effect is applied to the `out_color.rgb`.
    *   The highlight's intensity is determined by the distance from the sprite's horizontal center (`p`) and the `HIGHLIGHT_SIZE`.
    *   The `data.rgb` uniform provides the color of the highlight.
4.  **Vertex Color Multiplication**: The `out_color` is multiplied by `gl_Color` (the vertex color), which can be used for additional color tinting or effects.
5.  **Final Output**: The resulting `out_color` is assigned to `gl_FragColor`, which is the final color of the pixel.