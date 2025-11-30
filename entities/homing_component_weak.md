---
title: Homing Component (Weak)
category: entities
---

# Homing Component (Weak)

This entity defines a weak homing behavior for projectiles or entities.

## HomingComponent

This component grants an entity the ability to home in on a target.

### Key Attributes:

*   **`homing_targeting_coeff`**: Controls how strongly the entity attempts to target its destination. A higher value means more aggressive targeting.
*   **`homing_velocity_multiplier`**: Adjusts the entity's velocity when homing. A value close to 1 means minimal change, while lower values will slow it down.
*   **`detect_distance`**: The maximum distance at which the entity can detect and begin homing towards its target.