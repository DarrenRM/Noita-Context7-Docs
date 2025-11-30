---
title: ImGui Text Shader
category: shaders
---

---

# ImGui Text Shader

This fragment shader is used for rendering text within the ImGui interface in Noita. It manipulates the color and alpha values of the text based on texture data and vertex colors.

## Uniforms

*   `tex`: A `sampler2D` uniform representing the texture containing the text glyphs.
*   `tex_size`: A `vec2` uniform representing the dimensions of the `tex` texture.

## Main Function

The `main` function is the core of the shader, determining the final color of each pixel.

### Vertex Texture Coordinates

*   `uv`: Calculated from `gl_TexCoord[0].xy`, these are the texture coordinates for the current fragment.

### Color Calculation

*   `color`: The base color is sampled from the `tex` uniform using the `uv` coordinates.
*   `gl_FragColor`: The final output color is a combination of the vertex color (`gl_Color`) and the sampled texture color. Specifically, the red channel of the texture (`color.r`) is used to modulate the alpha channel of the final fragment color, effectively controlling the transparency of the text based on the glyph's alpha mask. The RGB components of the final color are taken directly from the vertex color.