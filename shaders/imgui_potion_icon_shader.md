---
title: ImGui Potion Icon Shader
category: shaders
---

# ImGui Potion Icon Shader

This shader is used to render potion icons within the ImGui interface, applying visual effects for potion status and drinking animations.

## Key Uniforms

These are the primary variables that control the shader's behavior.

| Uniform     | Type | Description                                                                 |
| :---------- | :--- | :-------------------------------------------------------------------------- |
| `tex`       | `sampler2D` | The texture containing the potion icon.                                     |
| `data`      | `vec4` | Controls various visual aspects: `data.x` for status amount, `data.y` for drinking flash. |
| `tex_size`  | `vec2` | The dimensions of the `tex` texture in pixels.                              |

## Pixel Art Filtering

This section defines a function for applying a pixel-art-friendly texture filtering.

### `pixel_art_filter_uv` Function

This function modifies texture coordinates to achieve a crisp, pixelated look, especially useful for pixel art assets.

| Parameter       | Type | Description                                                                                             |
| :-------------- | :--- | :------------------------------------------------------------------------------------------------------ |
| `uv`            | `vec2` | The input texture coordinate.                                                                           |
| `tex_size_pixels` | `vec2` | The size of the texture in pixels.                                                                      |
| **Returns**     | `vec2` | The filtered texture coordinate.                                                                        |

**Note:** For this filtering to work correctly, the texture filtering mode must be set to bilinear.

## Grayscale Conversion

A helper function to convert colors to grayscale based on perceived luminosity.

### `to_luminosity_based_grayscale` Function

| Parameter | Type   | Description                                                              |
| :-------- | :----- | :----------------------------------------------------------------------- |
| `color`   | `vec4` | The input RGBA color.                                                    |
| **Returns** | `vec4` | The grayscale RGBA color.                                                |

## Main Shader Logic (`main` function)

This is the core of the shader, where the final pixel color is determined.

### Potion Status and Drinking Animation

The shader dynamically adjusts the potion icon's appearance based on `data.x` (status amount) and `data.y` (drinking flash).

-   **Status Bar:** A portion of the icon's vertical UV space is used to represent the potion's status. If the `status_amount` is less than the current vertical position, the potion is rendered with a darker tint, simulating a depleted state.
-   **Drinking Flash:** When `data.y` is non-zero, the potion icon flashes with a brighter, white color, indicating the drinking action.

### Color Blending

The final color is a combination of the original texture color, the vertex color (`gl_Color`), and the effects applied for status and drinking.