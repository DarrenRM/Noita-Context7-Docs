---
title: Sprite Stains Shader
category: shaders
---

# Sprite Stains Shader

This shader is responsible for applying "stain" effects to sprites in Noita, often used for visual cues like blood or dirt. It leverages multiple textures to achieve the effect, including the sprite itself, a reference UV map for stain placement, and the actual stain texture.

## Key Functionality

The shader's primary goal is to blend a stain texture onto a sprite based on specific UV coordinates and a fading mechanism.

### Uniforms

These are the input variables that control the shader's behavior.

| Uniform Name | Type   | Description                                                                                              |
| :----------- | :----- | :------------------------------------------------------------------------------------------------------- |
| `tex`        | sampler2D | The main sprite texture.                                                                                 |
| `tex2`       | sampler2D | A reference texture containing UV coordinates for where stains should be applied on the sprite.            |
| `tex3`       | sampler2D | The texture containing the actual stain graphics.                                                        |
| `data`       | vec4   | Controls atlas scaling (`xy`) and offset (`zw`) for the stain texture.                                   |
| `tex_size`   | vec2   | The pixel dimensions of the sprite texture, used for UV calculations.                                    |

### Pixel Art Filtering

The shader includes an optional `PIXEL_ART_FILTER` macro. When enabled, it applies a custom UV filtering technique to ensure crisp pixel art rendering, preventing unwanted blurring.

#### `pixel_art_filter_uv` Function

This helper function takes a UV coordinate and the texture size, returning a modified UV that adheres to pixel art rendering principles.

### Main Logic (`main` function)

1.  **UV Calculation:** It first calculates the sprite's UV coordinates, applying the pixel art filter if enabled.
2.  **Stain UV Retrieval:** It samples `tex2` using the sprite UV to get the base UV coordinates for the stain.
3.  **Stain Atlas Transformation:** The retrieved stain UVs are then scaled and offset using the `data` uniform to correctly map them within the stain atlas.
4.  **Color Sampling:** The sprite's color is sampled from `tex`, and the stain color is sampled from `tex3` using the transformed stain UVs.
5.  **Stain Fading:** The stain's alpha is modified based on its original Y-coordinate (`stain_uv_orig.y`), causing it to fade out towards the top of the sprite.
6.  **Color Blending:** The sprite color and stain color are blended. The stain's influence is determined by its alpha and a multiplier.
7.  **Vertex Color Application:** The final output color is multiplied by the vertex color (`gl_Color`), allowing for per-sprite color tinting.
8.  **Output:** The final calculated color is assigned to `gl_FragColor`.

## Key Attributes/Elements

*   **`tex` (Sprite Texture):** The base image being modified.
*   **`tex2` (Stain Reference UVs):** Crucial for defining *where* stains appear on the sprite.
*   **`tex3` (Stain Texture):** The actual visual pattern of the stain.
*   **`data` (Atlas Scaling/Offset):** Essential for correctly positioning and sizing stains within a larger texture atlas.
*   **Stain Fading Logic:** The `min( stain_uv_orig.y + 0.35, 1.0 )` line is key to the vertical fading of stains.
*   **Blending Logic:** `mix( color.rgb, stain.rgb, min( stain.a * 1.5, 1.0 ) )` controls how the stain color replaces the sprite color.
*   **Pixel Art Filtering:** The `PIXEL_ART_FILTER` macro and `pixel_art_filter_uv` function ensure sharp visuals.