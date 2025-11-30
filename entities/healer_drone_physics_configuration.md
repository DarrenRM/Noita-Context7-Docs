---
title: Healer Drone Physics Configuration
category: entities
---

# Healer Drone Physics Configuration

This document details the physics and damage-related components for the Healer Drone entity in Noita, specifically focusing on its AI-driven movement and resilience.

## PhysicsAIComponent

This component governs the drone's physics-based movement and AI.

### Key Attributes:

*   **`target_vec_max_len`**: Maximum length of the vector used to guide the drone towards its target.
*   **`force_coeff`**: Coefficient for applying directional force.
*   **`force_balancing_coeff`**: Coefficient for balancing forces to maintain stability.
*   **`force_max`**: Maximum force that can be applied.
*   **`torque_coeff`**: Coefficient for applying rotational force.
*   **`torque_balancing_coeff`**: Coefficient for balancing rotational forces.
*   **`torque_max`**: Maximum torque that can be applied.
*   **`damage_deactivation_probability`**: Percentage chance the drone will deactivate upon taking damage.
*   **`damage_deactivation_time_min`**: Minimum duration (in frames) the drone remains deactivated after taking damage.
*   **`damage_deactivation_time_max`**: Maximum duration (in frames) the drone remains deactivated after taking damage.

```xml
<PhysicsAIComponent
    target_vec_max_len="15.0"
    force_coeff="20.0"
    force_balancing_coeff="0.8"
    force_max="100"
    torque_coeff="50"
    torque_balancing_coeff="0.8"
    torque_max="50.0"
    damage_deactivation_probability="20"
    damage_deactivation_time_min="30"
    damage_deactivation_time_max="100" >
</PhysicsAIComponent>
```

## DamageModelComponent

This component defines the drone's health.

### Key Attributes:

*   **`hp`**: Current health points.
*   **`max_hp`**: Maximum health points.

```xml
<DamageModelComponent
  hp="0.75"
  max_hp="0.75"
></DamageModelComponent >
```

## GameEffectComponent

This component applies a specific game effect to the entity.

### Key Attributes:

*   **`effect`**: The type of game effect applied. In this case, `PROTECTION_FREEZE`.
*   **`frames`**: Duration of the effect in frames. `-1` indicates a permanent effect.

```xml
<GameEffectComponent
    effect="PROTECTION_FREEZE"
    frames="-1"
>
</GameEffectComponent >
```