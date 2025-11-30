---
title: Projectile Homing Component
category: entities
---

# Projectile Homing Component

This entity defines a component that grants projectiles a homing ability.

## HomingComponent

This is the core component responsible for the homing behavior.

### Key Attributes:

*   **`target_who_shot`**: (Boolean) If `1`, the projectile will attempt to home in on the entity that fired it.
*   **`homing_targeting_coeff`**: (Float) Controls the strength of the homing effect. Higher values mean more aggressive targeting.
*   **`homing_velocity_multiplier`**: (Float) A multiplier applied to the projectile's velocity when homing. Values less than 1 will slow the projectile slightly while homing.
*   **`detect_distance`**: (Float) The maximum distance at which the projectile can detect and target its intended target.