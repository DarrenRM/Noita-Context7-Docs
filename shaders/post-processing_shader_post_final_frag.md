---
title: Post-Processing Shader (post_final.frag)
category: shaders
---

# Post-Processing Shader (post_final.frag)

This fragment shader is responsible for applying a wide range of post-processing effects to the rendered scene in Noita. It takes various texture inputs and uniform variables to manipulate the final image, including lighting, fog, color grading, and special effects.

## Key Uniforms

These are the primary variables that control the shader's behavior.

| Uniform Name                     | Type    | Description                                                                                             |
| :------------------------------- | :------ | :------------------------------------------------------------------------------------------------------ |
| `tex_bg`                         | sampler2D | Background texture.                                                                                     |
| `tex_fg`                         | sampler2D | Foreground texture.                                                                                     |
| `tex_lights`                     | sampler2D | Lighting information texture.                                                                           |
| `tex_skylight`                   | sampler2D | Skylight contribution texture.                                                                          |
| `tex_noise`                      | sampler2D | Noise texture for dithering and other effects.                                                          |
| `tex_perlin_noise`               | sampler2D | Perlin noise texture for distortion and other effects.                                                  |
| `tex_glow_unfiltered`            | sampler2D | Unfiltered glow information.                                                                            |
| `tex_glow`                       | sampler2D | Filtered glow texture.                                                                                  |
| `tex_fog`                        | sampler2D | Fog of war and dust texture.                                                                            |
| `dithering_amount`               | float   | Controls the intensity of dithering.                                                                    |
| `window_size`                    | vec2    | The size of the rendering window.                                                                       |
| `world_viewport_size`            | vec2    | The size of the world viewport.                                                                         |
| `camera_pos`                     | vec2    | The camera's position in the world.                                                                     |
| `camera_inv_zoom_ratio`          | float   | The inverse of the camera's zoom ratio.                                                                 |
| `time`                           | float   | The current game time, used for animations and time-based effects.                                      |
| `night_amount`                   | float   | Controls the intensity of the night effect.                                                             |
| `sky_light_color`                | vec4    | The color of the skylight.                                                                              |
| `damage_flash_interpolation`     | float   | Interpolation factor for the damage flash effect.                                                       |
| `additive_overlay_color`         | vec4    | Color and alpha for an additive overlay.                                                                |
| `overlay_color`                  | vec4    | Color and alpha for a standard overlay.                                                                 |
| `overlay_color_blindness`        | vec4    | Color and alpha for a blindness overlay effect.                                                         |
| `low_health_indicator_alpha`     | float   | Alpha value for the low health indicator.                                                               |
| `color_grading`                  | vec4    | Parameters for color grading.                                                                           |
| `brightness_contrast_gamma`      | vec4    | Parameters for brightness, contrast, and gamma correction.                                              |
| `fog_amount_background`          | float   | Controls fog amount for the background.                                                                 |
| `fog_amount_foreground`          | float   | Controls fog amount for the foreground.                                                                 |
| `drugged_distortion_amount`      | float   | Controls the intensity of distortion effects when drugged.                                              |
| `drugged_color_amount`           | float   | Controls the intensity of color effects when drugged.                                                   |
| `drugged_fractals_amount`        | float   | Controls the intensity of fractal effects when drugged.                                                 |
| `drugged_fractals_size`          | float   | Controls the size of fractal effects when drugged.                                                      |
| `drugged_nightvision_amount`     | float   | Controls the intensity of night vision effects when drugged.                                            |
| `drugged_doublevision_amount`    | float   | Controls the intensity of double vision effects when drugged.                                           |
| `tex_debug`                      | sampler2D | Debug texture 1.                                                                                        |
| `tex_debug2`                     | sampler2D | Debug texture 2.                                                                                        |

## Key Varying Variables

These variables are passed from the vertex shader and provide per-pixel information.

| Varying Name                | Type | Description                                                               |
| :-------------------------- | :--- | :------------------------------------------------------------------------ |
| `tex_coord_`                | vec2 | Texture coordinates for the main scene.                                   |
| `tex_coord_y_inverted_`     | vec2 | Inverted Y texture coordinates.                                           |
| `tex_coord_glow_`           | vec2 | Texture coordinates for the glow effect.                                  |
| `world_pos`                 | vec2 | World position of the pixel.                                              |
| `tex_coord_skylight`        | vec2 | Texture coordinates for the skylight.                                     |
| `tex_coord_fogofwar`        | vec2 | Texture coordinates for the fog of war.                                   |

## Core Functionality

The shader performs the following main operations:

### 1. Texture Coordinate Manipulation

*   **Liquid Distortion/Refraction:** Applies a distortion effect to texture coordinates based on liquid masks and time, simulating refraction through liquids.
*   **Trippy Distortion:** Warps texture coordinates using Perlin noise and time-based functions for psychedelic effects.
*   **Double Vision:** Creates a slight offset for foreground and background textures to simulate double vision.

### 2. Texture Sampling and Blending

*   **Base Color:** Samples the background (`tex_bg`) and foreground (`tex_fg`) colors.
*   **Glow:** Samples and processes the glow texture (`tex_glow`), applying smoothing and dithering for a better visual appearance.
*   **Lighting:** Samples the lighting texture (`tex_lights`) and combines it with skylight contributions.
*   **Fog of War:** Samples the fog texture (`tex_fog`) to apply fog of war and dust effects.

### 3. Lighting and Color Effects

*   **Skylight:** Calculates ambient lighting based on the `tex_skylight` texture and `sky_light_color`.
*   **Fog of War:** Modulates the final color based on the fog of war mask.
*   **Fog:** Applies atmospheric fog to both background and foreground elements.
*   **Night Vision:** Enhances brightness in darker areas, controlled by `drugged_nightvision_amount`.
*   **Color Grading:** Applies color adjustments using `color_grading` and `brightness_contrast_gamma` uniforms.
*   **Glow Blending:** Integrates the glow effect into the final image, with modulation based on skylight.
*   **Damage Flash:** Applies a red flash effect when the player takes damage.
*   **Shroom Color Effect:** Modulates the green channel of the color based on time and `drugged_color_amount`.
*   **Additive Overlay:** Adds a color overlay with transparency.
*   **Overlay:** Applies a standard color overlay.
*   **Blindness Overlay:** Applies a blindness effect, intensified at screen edges.
*   **Low Health Indicator:** Adds a red tint that intensifies towards the screen edges when health is low.

### 4. Dithering and Debugging

*   **Dithering:** Applies dithering to reduce banding and improve color transitions, controlled by `dithering_amount` and noise textures.
*   **Debug Visualizations:** Includes conditional compilation (`#ifdef`) for various debug overlays, such as skylight, noise patterns, and pathfinding data.

## Key Shader Features and Techniques

*   **`#define` Directives:** Used for enabling/disabling features like `DITHER`, `HIQ` (High Quality), and `TRIPPY` effects.
*   **`uniform` Variables:** Allow external control over shader parameters, essential for dynamic game effects.
*   **`varying` Variables:** Pass interpolated data from the vertex shader to the fragment shader.
*   **Texture Sampling:** Utilizes multiple textures to gather different visual components of the scene.
*   **Color Space Conversion:** Includes fast approximations for sRGB to linear and linear to sRGB conversions (`srgb2lin_fast`, `lin2srgb_fast`).
*   **Mathematical Functions:** Employs trigonometric functions (`sin`, `cos`, `atan`), interpolation (`mix`), clamping (`clamp`), and power functions (`pow`, `sqrt`) for complex visual effects.
*   **Conditional Logic:** Uses `if` statements and `step` functions to apply effects based on texture values or uniform parameters.
*   **Dithering Functions:** `dither` and `dither_srgb` are used to reduce color banding.
*   **Trippy Effect (`TRIPPY`):** A complex set of functions (`mlength`, `rotate`, `sinp`, `sinr`, `shape`, `render`) that create abstract, fractal-like visuals.
*   **High Quality (`HIQ`):** Enhances visual quality by sampling textures multiple times for smoothing and reducing aliasing artifacts.
*   **Debug Modes:** Allows developers to visualize internal shader data for debugging purposes.