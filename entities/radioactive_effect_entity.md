---
title: Radioactive Effect Entity
category: entities
---

# Radioactive Effect Entity

This entity defines the visual and functional aspects of the "Radioactive" game effect in Noita. It's primarily used to create a persistent visual hazard that damages players over time.

## Key Components

### `GameEffectComponent`

This component dictates the core behavior of the effect.

| Attribute        | Description                                                                 |
| :--------------- | :-------------------------------------------------------------------------- |
| `effect`         | Specifies the type of game effect. Set to `"RADIOACTIVE"`.                 |
| `frames`         | The duration of the effect in frames. `600` frames is equivalent to 10 seconds. |

### `ParticleEmitterComponent`

This component handles the visual representation of the radioactive hazard, emitting particles to simulate its presence.

| Attribute                 | Description