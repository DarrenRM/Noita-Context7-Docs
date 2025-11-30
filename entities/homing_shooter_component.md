---
title: Homing Shooter Component
category: entities
---

# Homing Shooter Component

This component enables an entity to home in on its target.

## Key Attributes

*   **`target_who_shot`**: Specifies who the entity should target. `1` typically means the entity that fired this projectile.
*   **`homing_targeting_coeff`**: Controls the strength of the homing behavior. Higher values mean more aggressive targeting.
*   **`homing_velocity_multiplier`**: Adjusts the projectile's velocity when homing. A value close to `1.0` means minimal change.
*   **`detect_distance`**: The maximum distance at which the entity can detect its target.

## Usage

This component is typically attached to projectiles or entities that need to pursue a specific target after being launched or spawned.

```xml
<Entity>
    <HomingComponent
        target_who_shot="1"
        homing_targeting_coeff="30.0"
        homing_velocity_multiplier="0.99"
        detect_distance="300"
    >
    </HomingComponent>
</Entity>
```