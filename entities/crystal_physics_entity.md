---
title: Crystal Physics Entity
category: entities
---

# Crystal Physics Entity

This document describes the `crystal_physics.xml` entity, which defines a crystalline creature with specific physics and damage behaviors.

## Key Components

### PhysicsAIComponent

This component governs the AI behavior related to physics interactions.

| Attribute                      | Description                                                                 |
| :----------------------------- | :-------------------------------------------------------------------------- |
| `damage_deactivation_probability` | The probability (in percent) that the entity will deactivate upon taking damage. |
| `damage_deactivation_time_min` | The minimum duration (in frames) the entity remains deactivated after taking damage. |
| `damage_deactivation_time_max` | The maximum duration (in frames) the entity remains deactivated after taking damage. |

### DamageModelComponent

This component defines the health and damage-related properties of the entity.

| Attribute                | Description                                                              |
| :----------------------- | :----------------------------------------------------------------------- |
| `hp`                     | The current health points of the entity.                                 |
| `max_hp`                 | The maximum health points the entity can have.                           |
| `minimum_knockback_force` | The minimum force required to cause knockback to this entity. This is a very high value, suggesting resistance to knockback. |