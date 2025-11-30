---
title: Sprite Cellgrid Preprocessed Shader
category: shaders
---

# Sprite Cellgrid Preprocessed Shader

This shader implements a pixel art friendly texture filtering technique for sprites. It aims to maintain sharp edges and prevent blurring when textures are scaled or sampled at different resolutions.

## Key Functionality

### `pixel_art_filter_uv` Function

This function is the core of the pixel art filtering. It takes a UV coordinate and the texture size in pixels and returns a modified UV coordinate that results in a pixelated appearance.

*   **Purpose:** To create a "pixel art friendly" texture coordinate.
*   **Mechanism:** It manipulates the UV coordinates based on the `alpha` constant and the texture size to achieve a stepped filtering effect.
*   **`alpha` Constant:** Controls the size of the "smoothly filtered border" between virtual art pixels. A smaller `alpha` value leads to sharper transitions.
*   **Texture Filtering Mode:** This technique relies on the texture's filtering mode being set to **bilinear** for it to work correctly.

### `main` Function

The main function of the shader.

*   **UV Calculation:** It calls `pixel_art_filter_uv` to get the filtered UV coordinates.
*   **Texture Sampling:** It samples the texture (`tex`) using the calculated UV coordinates.
*   **Output:** The sampled color is assigned to `gl_FragColor`, which is the final output color of the fragment.

## Uniforms

*   `tex`: A `sampler2D` representing the texture to be sampled.
*   `tex_size`: A `vec2` representing the dimensions of the texture in pixels.

## Preprocessor Directives

*   `#ifdef PIXEL_ART_FILTER`: This directive enables the pixel art filtering logic. If this macro is defined, the `pixel_art_filter_uv` function will contain the filtering code.
*   `#else`: If `PIXEL_ART_FILTER` is not defined, a simpler version of `pixel_art_filter_uv` is used, which simply returns the original UV coordinates, effectively disabling the pixel art filtering.