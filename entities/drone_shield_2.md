---
title: Drone Shield 2
category: entities
---

# Drone Shield 2

This entity defines a secondary energy shield for drones, likely used as a visual effect or a minor defensive component. It inherits its core functionality from `animal_energy_shield.xml`.

## Key Components

### EnergyShieldComponent
This component governs the shield's properties:

*   **recharge_speed**: `0.6` - How quickly the shield regenerates energy.
*   **radius**: `24.0` - The size of the shield's protective area.
*   **max_energy**: `1.5` - The maximum energy capacity of the shield.

### ParticleEmitterComponent (x3)
These components are responsible for emitting visual particles.

*   **First Emitter**:
    *   `is_emitting`: `0` - This emitter is initially inactive, suggesting it might be triggered by specific game events.

*   **Second and Third Emitters**:
    *   `emitted_material_name`: `plasma_fading_pink` - The material used for the emitted particles, creating a pink, fading plasma effect.
    *   `area_circle_radius.min`: `24`
    *   `area_circle_radius.max`: `24` - Both emitters are configured to release particles in a circular area with a radius of 24, matching the shield's radius.

## Inheritance

*   The entity inherits its base properties and behavior from `data/entities/misc/animal_energy_shield.xml`. This implies it shares fundamental mechanics with other energy shields in the game.