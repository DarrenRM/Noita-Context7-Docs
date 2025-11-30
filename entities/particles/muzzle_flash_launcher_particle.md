---
title: Muzzle Flash Launcher Particle
category: entities/particles
---

# Muzzle Flash Launcher Particle

This entity defines a muzzle flash effect for launchers in Noita. It utilizes a sprite animation and a particle emitter to create a visual burst of sparks.

## Key Components

### SpriteComponent

This component handles the visual appearance of the muzzle flash.

| Attribute           | Description                                                                                             |
| :------------------ | :------------------------------------------------------------------------------------------------------ |
| `image_file`        | Specifies the sprite sheet for the muzzle flash animation. Uses a numbered sequence `muzzle_launcher_0$[1-5].png`. |
| `rect_animation`    | The name of the animation to play from the sprite sheet.                                                |
| `next_rect_animation` | The name of the animation to transition to after the current one finishes.                              |
| `emissive`          | Makes the sprite glow.                                                                                  |
| `additive`          | Enables additive blending for the sprite, making it brighter when overlapping.                            |
| `kill_entity_after_finished` | The entity will be destroyed once the sprite animation is complete.                               |
| `offset_x`          | Horizontal offset for the sprite.                                                                       |
| `offset_y`          | Vertical offset for the sprite.                                                                         |

### ParticleEmitterComponent

This component generates small "spark" particles to accompany the muzzle flash.

| Attribute                 | Description