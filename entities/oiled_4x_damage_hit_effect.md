---
title: Oiled 4x Damage Hit Effect
category: entities
---

# Oiled 4x Damage Hit Effect

This entity defines a special hit effect that triggers when an entity is in the "OILED" status. When this condition is met, it applies a "DAMAGE_BOOST" effect with a value of 4.

## Key Components

### HitEffectComponent

This component is responsible for defining the conditions and effects of a hit.

| Attribute         | Value      | Description                                                                 |
| :---------------- | :--------- | :-------------------------------------------------------------------------- |
| `condition_status`| `OILED`    | The status effect that must be active on the target for this effect to trigger. |
| `effect_hit`      | `DAMAGE_BOOST` | The type of effect to apply when the condition is met.                      |
| `value`           | `4`        | The magnitude of the `DAMAGE_BOOST` effect. In this case, it multiplies damage by 4. |