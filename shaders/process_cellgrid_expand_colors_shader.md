---
title: Process Cellgrid Expand Colors Shader
category: shaders
---

# Process Cellgrid Expand Colors Shader

This GLSL fragment shader is designed to process a cell grid texture, specifically addressing transparent pixels (alpha = 0.0) to prevent black edges in pixel art anti-aliasing.

## Purpose

The primary goal of this shader is to sample the colors of neighboring pixels when a pixel has zero alpha. This effectively "expands" the color of transparent areas, blending them with adjacent non-transparent pixels. This technique is crucial for achieving smooth anti-aliasing on pixel art assets, preventing the appearance of harsh black outlines where transparency should be.

## Key Functionality

### Alpha Check and Neighbor Sampling

The core logic resides within the `main` function. It first checks the alpha channel (`color.a`) of the current pixel.

*   **If `color.a == 0.0` (transparent):**
    *   The shader calculates the size of a single pixel in texture coordinates (`px`).
    *   It then samples the four immediate neighbors: left, right, up, and down.
    *   A weighted average of these neighboring colors is computed, where the weight is determined by the alpha of each neighbor. This ensures that more opaque neighbors contribute more to the blended color.
    *   The resulting blended color is assigned to the current pixel, with its alpha set back to 0.0.

*   **If `color.a != 0.0` (opaque or semi-transparent):**
    *   The original color of the pixel is retained.

### Output

The final processed color is assigned to `gl_FragColor`, which is then rendered to the screen.

## Uniforms

*   `tex`: A `sampler2D` uniform representing the input texture (the cell grid).
*   `tex_size`: A `vec2` uniform representing the dimensions (width and height) of the input texture. This is used to calculate the pixel size for neighbor sampling.

## Technical Details

*   **GLSL Version:** `#version 110` indicates the use of an older GLSL version.
*   **Texture Coordinates:** `gl_TexCoord[0].xy` provides the texture coordinates for the current fragment.
*   **Color Representation:** Colors are represented as `vec4`, with components for Red, Green, Blue, and Alpha.
*   **Neighbor Sampling:** The shader uses `texture2D` to sample colors from the input texture at slightly offset UV coordinates.
*   **Weighted Averaging:** The calculation of `color_near` demonstrates a weighted average, crucial for accurate blending.

## Usage in Modding

This shader is likely used in conjunction with other shaders or rendering pipelines that require clean anti-aliasing for pixel art assets. Modders might encounter this shader when dealing with custom textures or visual effects that involve sprite rendering and transparency. Understanding its function can help in debugging or modifying visual elements that exhibit unexpected black edges.