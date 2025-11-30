---
title: Free Camera Light Entity
category: entities
---

# Free Camera Light Entity

This entity defines a light source that can be used for debugging or special effects within Noita. It's designed to be attached to an entity and emit light.

## Key Components

### LightComponent

This component is responsible for defining the properties of the light emitted by the entity.

| Attribute      | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `r`            | Red component of the light's color (0-255).                                 |
| `g`            | Green component of the light's color (0-255).                               |
| `b`            | Blue component of the light's color (0-255).                                |
| `radius`       | The maximum distance the light will illuminate.                             |
| `fade_out_time`| The time in seconds it takes for the light to completely fade out.        |

**Note:** This specific entity includes two identical `LightComponent` instances. In practice, one is usually sufficient unless specific layering or effects are intended.