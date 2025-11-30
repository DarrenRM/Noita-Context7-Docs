---
title: Teleportation Target Particle Effect
category: entities
---

# Teleportation Target Particle Effect

This entity defines the visual particle effect that appears when a teleportation spell targets an area. It's designed to be a brief, dissipating burst of energy.

## Key Components

### SpriteParticleEmitterComponent

This component controls the emission of particles that form the visual effect.

| Attribute                 | Description                                                                                                |
| :------------------------ | :--------------------------------------------------------------------------------------------------------- |
| `sprite_file`             | Specifies the sprite to be used for the particles (`data/particles/teleparticle.xml`).                     |
| `lifetime`                | The duration each individual particle exists (0.4 seconds).                                                |
| `color.r`, `color.g`, `color.b`, `color.a` | Initial color of the particles (fully white).                                                              |
| `color_change.a`          | How the alpha (transparency) of particles changes over their lifetime (-0.2, meaning they fade out).       |
| `scale.x`, `scale.y`      | Initial scale of the particles (width 1, height 0.2).                                                      |
| `scale_velocity.x`, `scale_velocity.y` | How the scale of particles changes over their lifetime (x shrinks, y grows).                               |
| `count_min`, `count_max`  | The number of particles emitted per emission event (4 to 5).                                               |
| `randomize_position.min_x`, `randomize_position.max_x` | Random horizontal offset for particle emission (-5 to 5 units).                                            |
| `randomize_velocity.min_y`, `randomize_velocity.max_y` | Random vertical velocity applied to particles (-40 to 40 units).                                           |
| `randomize_lifetime.min`, `randomize_lifetime.max` | Random variation in particle lifetime (-0.45 to 0.2 seconds).                                              |

### LifetimeComponent

This component governs the lifespan of the entity itself and its relationship with its parent.

| Attribute    | Description                                                              |
| :----------- | :----------------------------------------------------------------------- |
| `lifetime`   | The total duration this entity (the particle emitter) exists (5 seconds). |
| `kill_parent` | If set to 1, this entity will kill its parent entity upon its own death. |