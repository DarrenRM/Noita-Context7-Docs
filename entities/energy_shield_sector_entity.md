---
title: Energy Shield Sector Entity
category: entities
---

# Energy Shield Sector Entity

This entity defines a sector-based energy shield, typically used for defensive purposes on enemies or environmental hazards. It inherits its core functionality from `animal_energy_shield.xml` and modifies its shape and behavior.

## Key Components and Attributes

### Base Entity Inheritance

*   **`Base file="data/entities/misc/animal_energy_shield.xml"`**: This indicates that `animal_energy_shield_sector.xml` inherits all properties and components from the base `animal_energy_shield.xml` entity. Modifications in this file will override or add to the base.

### `InheritTransformComponent`

*   **`rotate_based_on_x_scale="1"`**: Allows the shield to rotate based on the scaling of its X-axis, useful for dynamic orientation.
*   **`Transform position.x="0" position.y="-4"`**: Defines the local offset of this entity relative to its parent. In this case, it's slightly offset on the Y-axis.

### `EnergyShieldComponent`

*   **`sector_degrees="170"`**: This is the primary attribute defining the shield's shape. It creates a shield that covers 170 degrees of a circle, leaving a gap.

### `ParticleEmitterComponent`

This entity utilizes multiple `ParticleEmitterComponent` instances to create visual effects associated with the shield.

*   **`area_circle_sector_degrees="170"`**: Each particle emitter is configured to emit particles within the same 170-degree sector as the shield itself, ensuring visual consistency.

## Summary

The `animal_energy_shield_sector.xml` entity is a specialized version of a standard energy shield. Its key characteristic is the `sector_degrees="170"` attribute in the `EnergyShieldComponent`, which limits the shield's coverage to a specific arc rather than a full circle. This is complemented by particle emitters that also operate within this defined sector, creating a visually distinct defensive mechanism.