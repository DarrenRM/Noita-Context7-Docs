---
title: Drone Shield 1
category: entities
---

# Drone Shield 1

This entity defines a basic energy shield, likely intended for drones or similar entities. It inherits its core functionality from `animal_energy_shield.xml` and customizes its shield properties and particle effects.

## Key Components

### EnergyShieldComponent

This component governs the shield's behavior.

| Attribute      | Value   | Description                                    |
|----------------|---------|------------------------------------------------|
| `recharge_speed` | `0.6`   | How quickly the shield regenerates energy.     |
| `radius`       | `16.0`  | The protective radius of the shield.           |
| `max_energy`   | `1.5`   | The maximum energy capacity of the shield.     |

### ParticleEmitterComponent

These components control visual effects.

*   **First Emitter:**
    *   `is_emitting`: `0` - This emitter is initially inactive.

*   **Second and Third Emitters:**
    *   `emitted_material_name`: `plasma_fading_pink` - The material used for the emitted particles.
    *   `area_circle_radius.min`: `16` - The minimum radius of the emission area.
    *   `area_circle_radius.max`: `16` - The maximum radius of the emission area.

These two emitters likely create a visual aura or effect around the shield, using pink fading plasma particles within a 16-unit radius.

## Inheritance

This entity inherits from `data/entities/misc/animal_energy_shield.xml`, meaning it will possess all the default behaviors and properties defined in that base file unless overridden here.