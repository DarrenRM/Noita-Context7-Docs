---
title: Drone Shield 3
category: entities
---

# Drone Shield 3

This entity defines a drone-like energy shield. It inherits its base functionality from `animal_energy_shield.xml` and customizes its energy properties and particle effects.

## Key Components

### Base Entity

*   **`Base file="data/entities/misc/animal_energy_shield.xml"`**: Inherits core behaviors and properties from a generic animal energy shield.

### EnergyShieldComponent

This component defines the shield's energy characteristics.

*   **`recharge_speed="0.6"`**: The rate at which the shield's energy replenishes.
*   **`radius="32.0"`**: The effective radius of the shield.
*   **`max_energy="1.5"`**: The maximum energy capacity of the shield.

### ParticleEmitterComponent (x3)

These components control the visual effects of the shield.

*   **First `ParticleEmitterComponent`**:
    *   **`is_emitting="0"`**: This specific emitter is disabled by default.

*   **Second `ParticleEmitterComponent`**:
    *   **`emitted_material_name="plasma_fading_pink"`**: The material used for the emitted particles, giving them a pink, fading appearance.
    *   **`area_circle_radius.min="32"`**: The minimum radius of the area from which particles are emitted.
    *   **`area_circle_radius.max="32"`**: The maximum radius of the area from which particles are emitted.

*   **Third `ParticleEmitterComponent`**:
    *   **`emitted_material_name="plasma_fading_pink"`**: Similar to the second emitter, uses pink fading plasma particles.
    *   **`area_circle_radius.min="32"`**: The minimum radius of the emission area.
    *   **`area_circle_radius.max="32"`**: The maximum radius of the emission area.

## Summary

The `drone_shield_3.xml` entity creates a functional energy shield with specific recharge rates, radius, and energy capacity. It utilizes pink plasma particles to visually represent the shield's presence and operation, with two emitters actively producing these effects within a 32-unit radius.