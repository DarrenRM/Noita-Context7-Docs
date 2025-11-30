---
title: Guts Explosion Trail Particle 03
category: entities/particles
---

# Guts Explosion Trail Particle 03

This entity defines a particle effect used in explosions, specifically a "guts" trail. It inherits its base properties from `explosion_trail_guts_01.xml`.

## Key Components

### PhysicsImageShapeComponent
This component defines the visual and physical properties of the particle.

| Attribute   | Value                 | Description                                     |
| :---------- | :-------------------- | :---------------------------------------------- |
| `image_file`| `data/particles/guts_03.png` | The sprite used for this particle.              |
| `material`  | `bone`                | The material type, influencing physics and interactions. |

### LuaComponent
This component adds custom behavior to the particle.

| Attribute         | Value | Description                                                              |
| :---------------- | :---- | :----------------------------------------------------------------------- |
| `execute_every_n_frame` | `4`   | The script logic within this component will execute every 4 frames. This is used to stagger the initialization of these particles, preventing them from sticking together too closely. |