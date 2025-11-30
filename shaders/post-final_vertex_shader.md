---
title: Post-Final Vertex Shader
category: shaders
---

# Post-Final Vertex Shader

This vertex shader is responsible for transforming vertex data and calculating texture coordinates for various post-processing effects in Noita. It handles camera positioning, zoom, and the generation of texture coordinates for skylight and fog-of-war effects.

## Key Uniforms

These uniforms provide essential data about the camera and rendering environment.

| Uniform Name                | Type   | Description                                                              |
| :-------------------------- | :----- | :----------------------------------------------------------------------- |
| `camera_pos`                | `vec2` | The world position of the camera.                                        |
| `camera_subpixel_offset`    | `vec2` | Subpixel offset for camera rendering, used for anti-aliasing.            |
| `world_viewport_size`       | `vec2` | The size of the game world's viewport.                                   |
| `camera_inv_zoom_ratio`     | `float`| The inverse of the camera's zoom ratio.                                  |
| `tex_skylight_sample_delta` | `vec2` | Delta offset for sampling the skylight texture.                          |
| `skylight_subpixel_offset`  | `vec2` | Subpixel offset for skylight texture sampling.                           |
| `tex_fog_sample_delta`      | `vec2` | Delta offset for sampling the fog-of-war texture.                        |
| `fog_subpixel_offset`       | `vec2` | Subpixel offset for fog-of-war texture sampling.                         |

## Key Varyings

These varyings pass calculated data from the vertex shader to the fragment shader.

| Varying Name              | Type   | Description                                                              |
| :------------------------ | :----- | :----------------------------------------------------------------------- |
| `tex_coord_`              | `vec2` | Primary texture coordinates.                                             |
| `tex_coord_y_inverted_`   | `vec2` | Y-inverted texture coordinates, adjusted by subpixel offset.             |
| `tex_coord_glow_`         | `vec2` | Texture coordinates for glow effects.                                    |
| `world_pos`               | `vec2` | The world position of the vertex.                                        |
| `tex_coord_skylight`      | `vec2` | Calculated texture coordinates for sampling the skylight texture.        |
| `tex_coord_fogofwar`      | `vec2` | Calculated texture coordinates for sampling the fog-of-war texture.      |

## Main Function Logic

The `main` function performs the core transformations and calculations.

### Vertex Transformation

```glsl
gl_Position = gl_ProjectionMatrix * gl_ModelViewMatrix * gl_Vertex;
gl_FrontColor = gl_Color;
gl_TexCoord[0] = gl_MultiTexCoord0;
gl_TexCoord[1] = gl_MultiTexCoord1;
```

This section sets the final vertex position in clip space and passes through color and initial texture coordinates.

### Coordinate Calculations

```glsl
tex_coord_ = gl_TexCoord[0].xy;
tex_coord_y_inverted_ = gl_TexCoord[0].zw + vec2(camera_subpixel_offset.x, camera_subpixel_offset.y);
tex_coord_glow_ = gl_TexCoord[1].xy;
world_pos = camera_pos + tex_coord_y_inverted_ * world_viewport_size;
```

Calculates primary, Y-inverted, and glow texture coordinates. `world_pos` is derived from camera position and scaled Y-inverted texture coordinates.

### Skylight Texture Coordinate Generation

```glsl
// world coordinates -> skylight texture coordinates
const float SKY_Y_OFFSET   = 55.0;
const float SKY_PIXEL_SIZE = 64.0;
const vec2  SKY_TEX_SIZE   = vec2( 32.0 );

sample_pos = tex_coord_y_inverted_ * world_viewport_size;
sample_pos.y += SKY_Y_OFFSET;
sample_pos   += ( ( SKY_TEX_SIZE * SKY_PIXEL_SIZE ) - world_viewport_size.x ) / 2.0;
sample_pos   += tex_skylight_sample_delta;
sample_pos   /= SKY_PIXEL_SIZE * SKY_TEX_SIZE;
sample_pos   += skylight_subpixel_offset;

tex_coord_skylight = sample_pos;
```

This block transforms world coordinates into normalized texture coordinates for the skylight effect. It involves applying offsets, scaling based on texture and pixel sizes, and incorporating sampling deltas and subpixel corrections.

### Fog-of-War Texture Coordinate Generation

```glsl
// world coordinates -> fog  texture coordinates
const float FOG_PIXEL_SIZE = 32.0;
float FOG_Y_OFFSET   = 90.0 * camera_inv_zoom_ratio;
vec2  FOG_TEX_SIZE   = vec2( 64.0 ) * camera_inv_zoom_ratio;

sample_pos = tex_coord_y_inverted_ * world_viewport_size;
sample_pos.y += FOG_Y_OFFSET;
sample_pos   += ( ( FOG_TEX_SIZE * FOG_PIXEL_SIZE ) - world_viewport_size.x ) / 2.0;
sample_pos   += tex_fog_sample_delta;
sample_pos   /= FOG_PIXEL_SIZE * FOG_TEX_SIZE;
sample_pos   += fog_subpixel_offset; // subpixel correction

tex_coord_fogofwar = sample_pos;
```

Similar to skylight, this section calculates texture coordinates for the fog-of-war effect. The offsets and sizes are dynamically adjusted based on the camera's zoom ratio.