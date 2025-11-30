---
title: Sprite Stains No Fade Shader
category: shaders
---

# Sprite Stains No Fade Shader

This shader is used to apply stains to sprites without fading, often for visual effects like blood or dirt that should appear sharply. It utilizes a pixel art filtering technique for crisp edges.

## Key Uniforms

These are the primary inputs that control the shader's behavior.

*   `tex`: Sampler for the main sprite texture.
*   `tex2`: Sampler for sprite reference pose UVs, used to determine stain placement.
*   `tex3`: Sampler for the reference pose stains texture.
*   `data`: A `vec4` uniform containing:
    *   `data.xy`: Atlas scale for stains.
    *   `data.zw`: Atlas offset for stains.
*   `tex_size`: A `vec2` uniform representing the size of the textures in pixels.

## Pixel Art Filtering

This section defines a function to create pixel art friendly texture coordinates.

### `pixel_art_filter_uv` Function

This function takes a UV coordinate and the texture size in pixels and returns a modified UV coordinate suitable for pixel art rendering.

*   **Purpose**: To achieve sharp, pixelated edges by simulating manual texture filtering.
*   **Requirement**: The texture filtering mode for the sprite texture must be set to bilinear for this trick to work correctly.
*   **`alpha` Constant**: A small `vec2` constant (e.g., `vec2(0.08)`) that influences the size of the smooth transition between virtual pixels.

## Main Shader Logic

The `main` function orchestrates the application of stains to the sprite.

1.  **Sprite UV Calculation**:
    *   The input UV coordinate (`gl_TexCoord[0].xy`) is processed by `pixel_art_filter_uv` using `tex_size` to get a pixel-art-friendly sprite UV.

2.  **Stain UV Determination**:
    *   `texture2D(tex2, sprite_uv)` retrieves the stain UV information from `tex2`.
    *   The retrieved stain UVs are then scaled and offset using the `data.xy` and `data.zw` uniforms, respectively.

3.  **Color Blending**:
    *   The main sprite color is sampled from `tex` using the calculated `sprite_uv`.
    *   The stain color is sampled from `tex3` using the adjusted stain UVs.
    *   The final color is a mix of the sprite's RGB and the stain's RGB. The mixing factor is determined by the stain's alpha (`stain.a`), clamped to a maximum of 1.0. This ensures stains appear sharply without fading.

4.  **Vertex Color Application**:
    *   The resulting `out_color` is multiplied by the vertex color (`gl_Color`), allowing for per-vertex color modulation.

5.  **Output**:
    *   The final calculated color is assigned to `gl_FragColor`.