---
title: Post Glow 1 Shader
category: shaders
---

# Post Glow 1 Shader

This shader is responsible for applying a post-processing glow effect to the game's visuals. It operates on the previous frame's glow texture to create a blurred and decayed effect.

## Key Uniforms

*   `tex_glow_prev_frame`: A `sampler2D` representing the glow texture from the previous frame. This is the primary input for the glow calculation.
*   `one_per_glow_texture_size`: A `vec2` containing the inverse dimensions of the glow texture. Used for calculating texture offsets.
*   `time`: A `float` representing the current game time. While present, it's not actively used in this specific shader's logic.

## Constants

*   `STEP`: Controls the increment for the blur loop.
*   `DECAY_COEFF`: A coefficient used in the decay calculation (though its direct impact is limited in this version).
*   `BLUR_RADIUS`: Defines the extent of the blur effect, determining how many steps are taken in each direction.

## Shader Logic

The `main` function performs the following:

1.  **Texture Coordinate Retrieval**: Gets the current texture coordinates from `gl_TexCoord[0].xy`.
2.  **Blur and Decay Loop**:
    *   Initializes a `decayed` `vec4` to zero.
    *   Calculates an `offset` based on `one_per_glow_texture_size` and a multiplier of 1.5.
    *   Iterates from `-BLUR_RADIUS` to `+BLUR_RADIUS` with a step defined by `STEP`.
    *   In each iteration, it samples the `tex_glow_prev_frame` at an offset position and adds the result to `decayed`. This effectively samples horizontally across the previous glow texture.
3.  **Decay Application**: The accumulated `decayed` color is multiplied by `0.1`.
4.  **Output**: The final `decayed` color is assigned to `gl_FragColor`, which becomes the output of this shader for the current frame.

This shader primarily implements a horizontal blur and a simple decay factor, contributing to the overall bloom or glow effect in Noita.