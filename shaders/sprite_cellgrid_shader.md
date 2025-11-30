---
title: Sprite Cellgrid Shader
category: shaders
---

# Sprite Cellgrid Shader

This shader implements a pixel art friendly texture filtering technique for sprites. It aims to maintain sharp edges and prevent blurring that can occur with standard bilinear filtering, especially when scaling pixel art.

## Key Functionality

The core of this shader is the `pixel_art_filter_uv` function, which manipulates texture coordinates to achieve a pixelated look.

### `pixel_art_filter_uv` Function

This function takes a UV coordinate and the texture size in pixels and returns modified UVs suitable for pixel art rendering.

*   **`alpha`**: A `vec2` constant (currently `vec2(0.08)`) that controls the size of the "smoothly filtered border" between virtual pixels. A smaller `alpha` value results in sharper transitions.
*   **UV Manipulation**: The function calculates fractional parts of the UVs and clamps them to create distinct pixel boundaries.
*   **Output**: Returns a `vec4` containing two sets of UV coordinates:
    *   `xy`: The calculated pixel-aligned UVs.
    *   `zw`: UVs for the center of the virtual pixel.

## `main` Function Logic

The `main` function orchestrates the shader's behavior, applying the pixel art filter when `PIXEL_ART_FILTER` is defined.

### Pixel Art Filtering (`#ifdef PIXEL_ART_FILTER`)

1.  **UV Calculation**: Calls `pixel_art_filter_uv` to get the specialized UVs.
2.  **Color Sampling**: Samples the texture using both the smoothed UVs (`uvs.xy`) and the center pixel UVs (`uvs.zw`).
3.  **Edge Handling**:
    *   It samples colors from neighboring pixels based on the center UVs.
    *   If the current pixel's alpha is 0.0 (transparent), it blends in the colors of the neighboring pixels, weighted by their alpha values. This helps to create smoother transitions for semi-transparent edges.
    *   If the smoothed color's alpha is less than 1.0, it uses the blended color for the final output.

### Standard Filtering (`#else`)

*   If `PIXEL_ART_FILTER` is not defined, it performs standard texture sampling using the provided UV coordinates.

## Uniforms

*   `tex`: A `sampler2D` representing the input texture.
*   `tex_size`: A `vec2` uniform representing the dimensions of the texture in pixels.

## Output

*   `gl_FragColor`: The final output color of the fragment, modulated by `gl_Color` (which typically represents vertex color or sprite tinting).