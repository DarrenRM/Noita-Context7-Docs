---
title: Default Vertex Shader
category: shaders
---

# Default Vertex Shader

This shader defines the fundamental vertex processing for Noita's graphics. It's a basic shader that transforms vertex positions and passes color and texture coordinates to the fragment shader.

## Purpose

The `default.vert` shader is the foundational vertex shader used by Noita. It handles the essential transformations required to render geometry in the game world.

## Key Elements

### `gl_Position`

*   **Description:** The final clip-space position of the vertex. This is the most crucial output of a vertex shader, determining where the vertex will be rendered on the screen.
*   **Calculation:** `gl_Position = gl_ProjectionMatrix * gl_ModelViewMatrix * gl_Vertex;`
    *   `gl_Vertex`: The input vertex position in model space.
    *   `gl_ModelViewMatrix`: A matrix that transforms vertices from model space to view space and then to camera space.
    *   `gl_ProjectionMatrix`: A matrix that transforms vertices from camera space to clip space.

### `gl_FrontColor`

*   **Description:** The color of the front-facing primitive. This color is interpolated across the primitive and passed to the fragment shader.
*   **Assignment:** `gl_FrontColor = gl_Color;`
    *   `gl_Color`: The input vertex color.

### `gl_TexCoord[0]`

*   **Description:** The first set of texture coordinates. These are typically used for the primary texture applied to a surface.
*   **Assignment:** `gl_TexCoord[0] = gl_MultiTexCoord0;`
    *   `gl_MultiTexCoord0`: The input texture coordinates from the first texture unit.

### `gl_TexCoord[1]`

*   **Description:** The second set of texture coordinates. These can be used for various purposes, such as lightmaps, secondary textures, or other shader effects.
*   **Assignment:** `gl_TexCoord[1] = gl_MultiTexCoord1;`
    *   `gl_MultiTexCoord1`: The input texture coordinates from the second texture unit.

## Usage in Modding

While this is a default shader, understanding its structure is fundamental for more advanced shader modifications. You would typically copy and modify this file to:

*   Introduce custom vertex transformations.
*   Pass additional data to the fragment shader.
*   Implement unique visual effects that require vertex manipulation.

## Version

*   `#version 110`: Specifies the GLSL (OpenGL Shading Language) version. This is an older version, indicating the game's engine might be using an older OpenGL context.