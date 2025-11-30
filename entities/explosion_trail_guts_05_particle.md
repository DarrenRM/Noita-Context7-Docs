---
title: Explosion Trail Guts 05 Particle
category: entities
---

---

# Explosion Trail Guts 05 Particle

This document describes the `explosion_trail_guts_05.xml` entity, which defines a specific particle effect used in Noita's explosions.

## Base Entity

This particle inherits its base properties from `data/entities/particles/particle_explosion/explosion_trail_guts_01.xml`.

## Key Components

### PhysicsImageShapeComponent

This component defines the visual and physical properties of the particle.

| Attribute   | Value                 | Description                                     |
| :---------- | :-------------------- | :---------------------------------------------- |
| `image_file`| `data/particles/guts_05.png` | The texture file used for the particle.       |
| `material`  | `bone`                | The material type, influencing physics and interactions. |

### LuaComponent

This component adds custom behavior to the particle using Lua scripting.

| Attribute           | Value | Description                                                                 |
| :------------------ | :---- | :-------------------------------------------------------------------------- |
| `execute_every_n_frame` | `6`   | The script within this component will execute every 6 frames. This is used to stagger the initialization of these "guts" particles, preventing them from sticking together too closely. |