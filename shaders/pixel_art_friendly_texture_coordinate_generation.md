---
title: Pixel Art Friendly Texture Coordinate Generation
category: shaders
---

---

# Pixel Art Friendly Texture Coordinate Generation

This shader function, `pixel_art_filter_uv`, is designed to generate texture coordinates that produce a pixel art aesthetic, specifically by simulating manual texture filtering. It aims to create sharp, distinct pixels rather than the smooth blending typically seen with bilinear filtering.

## Key Functionality

The core purpose of this function is to manipulate texture coordinates (`uv`) to achieve a pixelated look. It achieves this by:

*   **Scaling UVs:** The input `uv` coordinates are scaled by the texture's pixel dimensions (`tex_size_pixels`).
*   **Fractal Manipulation:** The fractional part of the scaled UVs is then processed. This is where the "pixel art" effect is generated.
*   **Clamping and Blending:** The `clamp` function is used to create a small, smoothly filtered border between virtual pixels. The `alpha` constant controls the size of this border.
*   **Floor and Re-scaling:** The manipulated fractional part is added back to the integer part (obtained via `floor`), and the result is then re-scaled back to the original UV space.

## Important Considerations

*   **Texture Filtering Mode:** For this shader trick to work correctly, the texture filtering mode **must be set to bilinear**. This function relies on the underlying texture sampling to behave in a specific way.
*   **`alpha` Constant:** The `alpha` constant (set to `vec2(0.07)` in the example) is crucial. It determines the size of the "smoothly filtered border" between virtual art pixels. Adjusting this value will change the perceived sharpness and blending of the pixel art.

## Function Signature

```glsl
vec2 pixel_art_filter_uv( vec2 uv, vec2 tex_size_pixels )
```

### Parameters

| Parameter         | Type  | Description                                                              |
| :---------------- | :---- | :----------------------------------------------------------------------- |
| `uv`              | `vec2` | The input texture coordinates (typically ranging from 0.0 to 1.0).       |
| `tex_size_pixels` | `vec2` | The dimensions of the texture in pixels (e.g., `vec2(textureWidth, textureHeight)`). |

### Returns

*   `vec2`: The modified texture coordinates, adjusted for pixel art rendering.

## Example Usage (Conceptual)

```glsl
// In your fragment shader:
uniform sampler2D u_texture;
uniform vec2 u_texture_size; // e.g., vec2(128.0, 128.0)

void main() {
    vec2 tex_coords = gl_TexCoord[0].st; // Or your texture coordinate source

    // Apply the pixel art filter
    vec2 filtered_uv = pixel_art_filter_uv(tex_coords, u_texture_size);

    // Sample the texture using the filtered coordinates
    vec4 pixel_color = texture2D(u_texture, filtered_uv);

    gl_FragColor = pixel_color;
}
```