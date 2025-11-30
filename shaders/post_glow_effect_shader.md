---
title: Post Glow Effect Shader
category: shaders
---

# Post Glow Effect Shader

This shader implements a post-processing effect to create a glow or bloom around bright areas of the screen. It accumulates glow from previous frames and blends it with the current frame's bright pixels.

## Key Uniforms

These are the primary inputs that control the shader's behavior.

| Uniform Name                     | Type    | Description