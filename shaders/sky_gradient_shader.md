---
title: Sky Gradient Shader
category: shaders
---

# Sky Gradient Shader

This shader defines the visual appearance of the sky gradient in Noita. It manipulates the input color based on texture coordinates to create a smooth transition.

## Key Functionality

The shader's primary purpose is to blend between a darker, desaturated version of the input color and the original input color. This blending is controlled by the `lerp` variable, which is derived from the texture's Y-coordinate.

### `main()` Function Breakdown

The `main()` function is the core of the shader, responsible for calculating the final pixel color.

1.  **Texture Coordinates:**
    *   `vec2 tex_coord = gl_TexCoord[0].xy;`
    *   Retrieves the texture coordinates for the current pixel. `tex_coord.y` is crucial for determining the gradient.

2.  **Input Colors:**
    *   `vec4 in_color = gl_Color;`
    *   The original color passed to the shader.
    *   `vec4 in_color_dark = in_color * vec4(0.5, 0.55, 0.7, 1.0);`
    *   A darker, slightly desaturated version of the input color. The multiplication factors (0.5, 0.55, 0.7) control the intensity and color shift.

3.  **Lerp (Linear Interpolation) Calculation:**
    *   `float lerp = clamp(tex_coord.y * 0.15, 0.0, 1.4) - 0.05;`
    *   This is the core logic for the gradient.
        *   `tex_coord.y * 0.15`: Scales the Y-coordinate. A higher Y-coordinate (closer to the top of the sky) will result in a larger value.
        *   `clamp(..., 0.0, 1.4)`: Restricts the scaled Y-coordinate to a range between 0.0 and 1.4. This prevents extreme values from causing unexpected results.
        *   `- 0.05`: An offset applied to the clamped value. This fine-tunes the starting point and range of the gradient.

4.  **Color Blending:**
    *   `vec4 color = mix( in_color_dark, in_color, lerp );`
    *   Uses the `mix` function to linearly interpolate between `in_color_dark` and `in_color` based on the `lerp` value.
        *   When `lerp` is close to 0, the color will be closer to `in_color_dark`.
        *   When `lerp` is close to 1, the color will be closer to `in_color`.
        *   Values of `lerp` outside the 0-1 range will result in the color being fully `in_color_dark` (if `lerp` < 0) or fully `in_color` (if `lerp` > 1), due to the `clamp` operation.

5.  **Output Color:**
    *   `gl_FragColor = color;`
    *   Sets the final color of the fragment (pixel) to the calculated blended color.

## Key Parameters for Modding

*   **`in_color`**: The base color provided to the shader. This is typically determined by the game's sky settings.
*   **`in_color_dark`**: The multiplier `vec4(0.5, 0.55, 0.7, 1.0)` controls how much the base color is darkened and shifted. Modifying these values will change the color of the lower part of the sky gradient.
*   **`tex_coord.y * 0.15`**: The multiplier `0.15` controls the "steepness" or spread of the gradient. A higher value makes the transition happen over a smaller vertical distance.
*   **`clamp(..., 0.0, 1.4)`**: The `0.0` and `1.4` define the minimum and maximum values for the `lerp` calculation. Adjusting these can change the overall range of the gradient.
*   **`- 0.05`**: The offset value. This shifts the entire gradient up or down.

## Example Modifications

*   **Brighter Sky:** Increase the values in `vec4(0.5, 0.55, 0.7, 1.0)` towards `1.0`.
*   **More Vibrant Colors:** Adjust the `in_color` input or slightly alter the multipliers in `in_color_dark`.
*   **Faster Gradient Transition:** Increase the `0.15` multiplier.
*   **Slower Gradient Transition:** Decrease the `0.15` multiplier.
*   **Shift Gradient Upwards:** Increase the `- 0.05` offset.
*   **Shift Gradient Downwards:** Decrease the `- 0.05` offset.