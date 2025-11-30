---
title: Fire Mage Entity
category: entities
---

# Fire Mage Entity

This document details the configuration for the Fire Mage entity in Noita, focusing on its combat and visual properties.

## Base Entity Properties

The Fire Mage inherits its core functionality from a base entity, with specific modifications.

### Damage Component

*   **hp**: 15 (Hit Points)
*   **max\_hp**: 15 (Maximum Hit Points)
*   **minimum\_knockback\_force**: 100000 (A very high value, indicating strong resistance to knockback)

## Visual and Particle Effects

The Fire Mage is characterized by its fiery aura and particle emissions, primarily originating from its hands.

### Main Body Particle Emitters

These emitters contribute to the general fiery appearance of the mage.

*   **InheritTransformComponent**: Positions the emitters relative to the main entity.
    *   `position.x`: 0
    *   `position.y`: -12 (Slightly above the entity's origin)
*   **Base file**: `data/entities/base_torch_particle.xml` (Inherits particle generation from a torch-like base)

#### ParticleEmitterComponent (General Glow)

*   `x_pos_offset_min`: -2
*   `x_pos_offset_max`: 2

#### ParticleEmitterComponent (Color Accent)

*   `color`: `ff3fe2df` (A bright, almost cyan-like glow)
*   `x_pos_offset_min`: -2
*   `x_pos_offset_max`: 2

#### ParticleEmitterComponent (Spark Effect)

*   `emitted_material_name`: `spark_blue` (Generates blue sparks)
*   `x_pos_offset_min`: -2
*   `x_pos_offset_max`: 2

#### ParticleEmitterComponent (Fire Effect)

*   `emitted_material_name`: `fire_blue` (Generates blue fire particles)

### Left Hand Particle Emitters

These emitters are specifically attached to the mage's left hand, creating a more focused visual effect.

*   **HotspotComponent**: Defines the "hand" as a hotspot for attachment.
    *   `_tags`: `hand_l`
    *   `sprite_hotspot_name`: `hand`
    *   `transform_with_scale`: 1
*   **Entity name**: `hand_l`

#### ParticleEmitterComponent (Hand Glow - Count)

*   `count_min`: 2
*   `count_max`: 3
*   `x_pos_offset_min`: -1
*   `x_pos_offset_max`: 1
*   `y_pos_offset_min`: -1
*   `y_pos_offset_max`: 2

#### ParticleEmitterComponent (Hand Glow - Color)

*   `color`: `ff3fe2df`
*   `count_min`: 2
*   `count_max`: 3
*   `x_pos_offset_min`: -1
*   `x_pos_offset_max`: 1
*   `y_pos_offset_min`: -1
*   `y_pos_offset_max`: 2

#### ParticleEmitterComponent (Hand Spark Effect)

*   `emitted_material_name`: `spark_blue`
*   `x_pos_offset_min`: -1
*   `x_pos_offset_max`: 1
*   `y_pos_offset_min`: -3
*   `y_pos_offset_max`: 2

#### ParticleEmitterComponent (Hand Fire Effect)

*   `emitted_material_name`: `fire_blue`

*   **InheritTransformComponent**: Attaches these particles to the `hand_l` hotspot.
    *   `parent_hotspot_tag`: `hand_l`
    *   `only_position`: 1 (Only position is inherited, not rotation or scale)