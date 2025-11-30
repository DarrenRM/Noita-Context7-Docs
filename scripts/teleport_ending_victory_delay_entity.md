---
title: Teleport Ending Victory Delay Entity
category: data/entities
---

# Teleport Ending Victory Delay Entity

This entity acts as a temporary placeholder or trigger for the victory teleportation sequence in Noita. It's designed to delay the actual teleportation event, allowing for visual or auditory cues to play out before the player is moved.

## Key Components

### LightComponent

This component defines a visual light effect associated with the entity.

| Attribute       | Description                                                                 |
| --------------- | --------------------------------------------------------------------------- |
| `_enabled`      | Whether the light component is active (1 for enabled).                      |
| `radius`        | The radius of the light effect.                                             |
| `fade_out_time` | The duration in seconds for the light to fade out.                          |
| `r`, `g`, `b`   | The RGB color values of the light.                                          |
| `offset_y`      | Vertical offset of the light source.                                        |

### SpriteParticleEmitterComponent

This component generates a particle effect, likely a swirling purple visual, to accompany the entity.

| Attribute                 | Description