---
title: ImGui Status Icon Shader
category: shaders
---

---

# ImGui Status Icon Shader

This shader is used to render status icons within the ImGui interface, allowing for visual representation of status effects or progress. It includes functionality for pixel art filtering and dynamically adjusting the icon's appearance based on a status amount.

## Key Features

### Pixel Art Filtering

The shader can optionally apply a pixel art friendly texture coordinate transformation. This is controlled by the `PIXEL_ART_FILTER` preprocessor directive. When enabled, it aims to create sharper, more defined pixelated visuals.

*   **`pixel_art_filter_uv(vec2 uv, vec2 tex_size_pixels)`**: This function takes UV coordinates and texture size, returning transformed UVs for pixel art rendering.
    *   **`alpha`**: A `vec2` uniform controlling the size of the smooth filtering border between virtual pixels.

### Status Rendering Logic

The core of the shader manipulates the icon's color based on a `status_amount` uniform.

*   **`data`**: A `vec4` uniform. `data.x` is interpreted as the `status_amount`.
*   **`status_amount`**: A float value, typically expected to be between `0.1` and `0.8`.
*   **`uv.y`**: The vertical component of the UV coordinates is used to determine the "fill" level of the status.
*   **Color Modification**: If the `status_amount` is less than a calculated threshold based on `uv.y`, the icon's RGB color is darkened (multiplied by `0.55`).

## Uniforms

| Name      | Type   | Description                                                              |
| :-------- | :----- | :----------------------------------------------------------------------- |
| `tex`     | `sampler2D` | The texture containing the icon.                                         |
| `data`    | `vec4` | Contains status information. `data.x` is the primary status amount.      |
| `tex_size`| `vec2` | The dimensions of the texture in pixels.                                 |

## Main Function Logic

1.  **UV Transformation**: Applies pixel art filtering to the input UV coordinates if enabled.
2.  **Texture Sampling**: Samples the `tex` uniform using the transformed UVs.
3.  **Color Application**: Multiplies the sampled color by `gl_Color` (vertex color).
4.  **Status Calculation**: Determines the `status_amount` from `data.x`.
5.  **Conditional Darkening**: Based on `status_amount` and the `uv.y` coordinate, the icon's RGB color may be darkened to visually represent a reduced status.
6.  **Output**: Sets the final `gl_FragColor`.

## Example Usage (Conceptual)

Imagine an icon representing a shield.

*   If `status_amount` is `0.8`, the icon appears fully.
*   If `status_amount` is `0.4`, a portion of the icon (visually represented by the darkening effect) might indicate reduced shield strength.