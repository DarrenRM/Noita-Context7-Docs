---
title: Sprite Default Fragment Shader
category: shaders
---

---

# Sprite Default Fragment Shader

This fragment shader is responsible for rendering sprites in Noita, applying a pixel art-friendly texture filtering method.

## Purpose

The primary goal of this shader is to ensure that sprites maintain a crisp, pixelated appearance, even when the game's rendering resolution or texture filtering settings might otherwise cause blurring.

## Key Features

### Pixel Art Filtering

The shader implements a custom texture coordinate manipulation technique to achieve a pixel art look. This is controlled by the `PIXEL_ART_FILTER` preprocessor directive.

*   **`#ifdef PIXEL_ART_FILTER`**: This block is active when the `PIXEL_ART_FILTER` macro is defined, enabling the pixel art filtering logic.
*   **`pixel_art_filter_uv` function**: This function takes the standard texture coordinates (`uv`) and the texture size in pixels (`tex_size_pixels`) as input. It then modifies the `uv` to simulate sharp pixel boundaries.
    *   **`alpha` uniform**: A small constant (`vec2(0.08)`) that controls the size of the smooth transition zone between virtual pixels. A smaller `alpha` results in sharper edges.
    *   The core logic involves calculating the fractional part of the UV coordinates and clamping it to create distinct pixel blocks.

### Standard Sprite Rendering

When `PIXEL_ART_FILTER` is not defined, the shader falls back to standard texture sampling.

*   **`#else` block**: This block is executed if `PIXEL_ART_FILTER` is not defined, returning the original `uv` coordinates without modification.

## Main Function (`main`)

The `main` function is the entry point for the shader's execution for each pixel.

1.  **UV Calculation**: It first calls `pixel_art_filter_uv` to get the potentially filtered texture coordinates.
2.  **Texture Sampling**: It samples the texture (`tex`) using the calculated `uv`.
3.  **Color Application**: The sampled color is then multiplied by the vertex color (`gl_Color`), which is typically used for per-sprite tinting or other vertex-based color effects.
4.  **Output**: The final calculated color is assigned to `gl_FragColor`, which is the output color for the current pixel.

## Uniforms

*   **`tex` (sampler2D)**: The texture containing the sprite's image data.
*   **`tex_size` (vec2)**: The dimensions of the texture in pixels.

## Notes for Modding

*   **Texture Filtering**: For the `pixel_art_filter_uv` function to work as intended, the texture filtering mode for sprites in Noita should be set to **bilinear**.
*   **Custom Shaders**: Modders can potentially create their own sprite shaders by modifying this file or creating new ones, allowing for unique visual effects on sprites.
*   **Performance**: The pixel art filtering adds a small computational cost. For performance-critical scenarios or if a blurred look is desired, disabling this filter might be considered.