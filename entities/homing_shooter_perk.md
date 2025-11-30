---
title: Homing Shooter Perk
category: entities
---

---

# Homing Shooter Perk

This entity defines the "Homing Shooter" perk in Noita. When acquired, projectiles fired by the player will gain homing capabilities.

## Key Components

### HomingComponent

This component governs the homing behavior of projectiles.

| Attribute                  | Description                                                                                                |
| :------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `target_who_shot`          | Specifies that the projectile should target the entity that fired it.                                      |
| `homing_targeting_coeff`   | Controls the strength of the homing effect. Higher values mean more aggressive targeting.                   |
| `homing_velocity_multiplier` | Adjusts the projectile's velocity while homing. A value less than 1.0 will slow it down slightly.        |
| `detect_distance`          | The maximum distance at which the projectile can detect its target.                                        |