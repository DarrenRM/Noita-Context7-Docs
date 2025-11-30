---
title: Water Electrocution Particle
category: entities
---

# Water Electrocution Particle

This entity defines the visual and electrical effects associated with water becoming electrified. It primarily uses a `SpriteParticleEmitterComponent` to spawn visual sparks and an `ElectricChargeComponent` to manage the electrical properties.

## Key Components

### ElectricChargeComponent

This component governs the electrical behavior of the entity.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `charge_time_frames`      | The duration (in frames) for which the entity holds an electrical charge.   |
| `electricity_emission_interval_frames` | How often (in frames) electrical energy is emitted.                     |
| `fx_velocity_max`         | The maximum velocity of emitted electrical effects (e.g., sparks).          |

### SpriteParticleEmitterComponent

This component is responsible for generating visual particles, in this case, electric sparks.

| Attribute                 | Description