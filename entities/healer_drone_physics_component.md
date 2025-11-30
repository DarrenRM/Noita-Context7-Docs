---
title: Healer Drone Physics Component
category: entities
---

# Healer Drone Physics Component

This document details the physics and damage-related components for the Healer Drone entity in Noita, intended for AI-assisted modding.

## PhysicsAIComponent

This component governs the drone's movement and physical interactions.

### Key Attributes:

*   **`target_vec_max_len`**: Maximum length of the target vector for movement. (Default: `15.0`)
*   **`force_coeff`**: Coefficient for applying directional force. (Default: `20.0`)
*   **`force_balancing_coeff`**: Coefficient for balancing applied force. (Default: `0.8`)
*   **`force_max`**: Maximum force that can be applied. (Default: `100`)
*   **`torque_coeff`**: Coefficient for applying rotational force. (Default: `50`)
*   **`torque_balancing_coeff`**: Coefficient for balancing applied torque. (Default: `0.8`)
*   **`torque_max`**: Maximum torque that can be applied. (Default: `50.0`)
*   **`damage_deactivation_probability`**: Probability (in percent) of deactivating upon taking damage. (Default: `20`)
*   **`damage_deactivation_time_min`**: Minimum duration (in frames) of deactivation after taking damage. (Default: `30`)
*   **`damage_deactivation_time_max`**: Maximum duration (in frames) of deactivation after taking damage. (Default: `100`)

## DamageModelComponent

This component defines the drone's health and damage resistances.

### Key Attributes:

*   **`hp`**: Current health points. (Default: `0.75`)
*   **`max_hp`**: Maximum health points. (Default: `0.75`)

### Damage Multipliers:

*   **`projectile`**: Multiplier for damage taken from projectiles. (Default: `0.0` - immune to projectiles)

## GameEffectComponent

This component applies a persistent game effect to the entity.

### Key Attributes:

*   **`effect`**: The type of game effect to apply. (Value: `PROTECTION_FREEZE`)
*   **`frames`**: Duration of the effect in frames. `-1` indicates infinite duration. (Value: `-1`)