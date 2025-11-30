---
title: Drone Physics Entity
category: entities
---

# Drone Physics Entity

This document describes the `drone_physics.xml` entity, a basic flying enemy with physics-based behavior and a freeze protection effect.

## Key Components

### DamageModelComponent
Manages the entity's health.

| Attribute | Value | Description |
|---|---|---|
| `hp` | 3.6 | Current health points. |
| `max_hp` | 3.6 | Maximum health points. |

### PhysicsAIComponent
Controls the entity's physics-based AI, including deactivation upon taking damage.

| Attribute | Value | Description |
|---|---|---|
| `damage_deactivation_probability` | 40 | Percentage chance to deactivate when damaged. |
| `damage_deactivation_time_min` | 40 | Minimum deactivation duration in frames. |
| `damage_deactivation_time_max` | 120 | Maximum deactivation duration in frames. |

### AnimalEnergyShieldComponent
(Inherited from `misc/animal_energy_shield.xml`)
Likely provides a basic energy shield for the drone. Specific attributes are not detailed in this snippet.

### GameEffectComponent
Applies a special effect to the entity.

| Attribute | Value | Description |
|---|---|---|
| `effect` | `PROTECTION_FREEZE` | The effect applied is immunity to freezing. |
| `frames` | -1 | The effect lasts indefinitely (-1 frames). |

### InheritTransformComponent
Ensures the entity inherits transformation properties from its parent.