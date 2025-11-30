---
title: Statue Physics Emissive Particle
category: particles
---

# Statue Physics Emissive Particle

This documentation describes the `statue_physics_emissive_particle.xml` file, which defines a particle effect used in Noita. This particle is likely associated with physics-enabled statues and features an emissive glow.

## Sprite

The `<Sprite>` element defines the visual appearance of the particle.

### Key Attributes:

*   **filename**: `data/particles/statue_physics_emissive_particle.png` - Specifies the texture file used for the particle.
*   **offset\_x**: `8` - Horizontal offset for the sprite.
*   **offset\_y**: `13` - Vertical offset for the sprite.
*   **default\_animation**: `fade` - The animation to play by default when the particle is created.

### Animations

#### `fade` Animation

This animation defines the fading effect for the particle.

*   **name**: `fade`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `12` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `24` - The height of each individual frame.
*   **frame\_wait**: `0.18` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `11` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (it plays once).