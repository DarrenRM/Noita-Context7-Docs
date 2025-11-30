---
title: Tank Rocket Entity
category: entities
---

# Tank Rocket Entity

This document describes the `tank_rocket.xml` entity, representing a rocket-propelled tank enemy in Noita.

## Key Attributes

### DamageModelComponent

This component defines the health and knockback resistance of the tank rocket.

| Attribute              | Description                                  |
| :--------------------- | :------------------------------------------- |
| `hp`                   | Current health points.                       |
| `max_hp`               | Maximum health points.                       |
| `minimum_knockback_force` | The minimum force required to knock back the entity. A very high value indicates significant resistance. |

### GameEffectComponent

This component applies a persistent game effect to the entity.

| Attribute | Description                                      |
| :-------- | :----------------------------------------------- |
| `effect`  | The type of game effect applied. `PROTECTION_FREEZE` means it's immune to freezing. |
| `frames`  | Duration of the effect in frames. `-1` indicates a permanent effect. |