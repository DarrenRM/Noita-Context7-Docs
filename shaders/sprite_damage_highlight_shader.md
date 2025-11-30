---
title: Sprite Damage Highlight Shader
category: shaders
---

---

# Sprite Damage Highlight Shader

This shader is designed to apply a damage highlight effect to sprites in Noita. It utilizes a pixel art-friendly texture filtering technique to maintain crisp edges while allowing for smooth transitions in the highlight.

## Key Functionality

### `pixel_art_filter_uv` Function

This function is the core of the pixel art filtering. It takes a texture coordinate (`uv`) and the texture size (`tex_size_pixels`) and returns a modified UV coordinate that simulates pixel art filtering.

*   **Purpose:** To create a sharp, pixelated look for textures, preventing blurring between virtual pixels.
*   **Mechanism:** It manipulates the fractional part of the UV coordinates to create a smooth transition zone, effectively "snapping" pixels to a grid.
*   **`alpha` Uniform:** Controls the size of the smooth border between virtual pixels. A smaller `alpha` results in sharper transitions.

### `main` Function

The main function of the shader.

*   **Texture Sampling:** It samples the texture using the `tex` uniform.
*   **UV Filtering:** It applies the `pixel_art_filter_uv` function to the texture coordinates to ensure pixel art rendering.
*   **Output Color:** The final output color is set to white (`1.0, 1.0, 1.0`) with the original alpha channel from the sampled texture. This effectively makes the sprite white, with its transparency preserved.

## Uniforms

*   `tex`: A `sampler2D` uniform representing the texture to be rendered.
*   `tex_size`: A `vec2` uniform representing the dimensions of the texture in pixels.

## Preprocessor Directives

*   `#define PIXEL_ART_FILTER`: Enables the pixel art filtering logic. If this is not defined, the `pixel_art_filter_uv` function will simply return the original UV coordinates.

## Usage Notes

*   This shader is intended to be applied to sprites that need a damage highlight effect.
*   The `PIXEL_ART_FILTER` should be enabled for the desired pixel art aesthetic.
*   The `tex_size` uniform must be correctly set to the dimensions of the `tex` uniform for the filtering to work as intended.