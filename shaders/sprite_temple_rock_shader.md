---
title: Sprite Temple Rock Shader
category: shaders
---

# Sprite Temple Rock Shader

This shader is used to render sprite textures, specifically for elements within the "temple rock" theme. It incorporates a pixel art filtering technique and applies color adjustments and a dissolve effect.

## Key Features

### Pixel Art Filtering

This shader includes an optional `PIXEL_ART_FILTER` that aims to create a pixelated look while maintaining some smoothness at the edges of virtual pixels.

*   **`pixel_art_filter_uv` function:**
    *   Takes a UV coordinate and texture size as input.
    *   Applies a mathematical transformation to achieve a pixelated effect.
    *   The `alpha` uniform controls the size of the smooth border between virtual pixels.
    *   Requires the texture filtering mode to be set to bilinear for this effect to work correctly.

### Color Adjustments

The shader applies several color modifications to the base texture.

*   **Desaturation:** A portion of the color information is removed, making the sprite appear less vibrant.
    ```glsl
    vec4 color_desaturated = vec4( dot( vec3(0.2126,0.7152,0.0722), color.rgb ) );
    color = vec4( mix( color, color_desaturated, 0.5 ).rgb, color.a ); // desaturate a little
    ```
*   **Tinting and Opacity Reduction:** The sprite is given a warmer tint and its overall opacity is reduced.
    ```glsl
    color *= vec4(0.85,0.7,0.6,0.5); // tint warmer, reduce opacity
    ```

### Dissolve Effect

A dissolve effect is implemented using a perlin noise texture.

*   **`tex2` uniform:** This sampler is used for the perlin noise texture.
*   **`dissolve_alpha` calculation:** The red channel of the perlin noise texture (`color_perlin.r`) is compared against the alpha value of the vertex color (`gl_Color.a`). This comparison, multiplied by the vertex alpha, determines the final dissolve alpha.
    ```glsl
    float dissolve_alpha = step( color_perlin.r, gl_Color.a ) * gl_Color.a;
    ```
*   **Final Fragment Color:** The calculated `dissolve_alpha` is applied to the fragment's alpha channel, controlling its transparency and creating the dissolve effect.
    ```glsl
    gl_FragColor = color * vec4( gl_Color.rgb, dissolve_alpha );
    ```

## Uniforms

| Uniform Name | Type    | Description                                                              |
| :----------- | :------ | :----------------------------------------------------------------------- |
| `tex`        | sampler2D | The main texture sampler for the sprite.                                 |
| `tex2`       | sampler2D | The texture sampler for perlin noise, used for the dissolve effect.    |
| `tex_size`   | vec2    | The size of the texture in pixels, used for pixel art filtering.       |

## Main Function Logic

1.  **UV Calculation:** The UV coordinates are processed by the `pixel_art_filter_uv` function to apply pixel art filtering if enabled.
2.  **Texture Sampling:** The main texture (`tex`) and the perlin noise texture (`tex2`) are sampled using the calculated UV coordinates.
3.  **Color Manipulation:** The sampled color undergoes desaturation and tinting.
4.  **Dissolve Alpha Calculation:** The `dissolve_alpha` is computed based on the perlin noise and vertex color.
5.  **Final Color Output:** The final fragment color is determined by multiplying the adjusted sprite color with the vertex color's RGB components and the calculated `dissolve_alpha`.