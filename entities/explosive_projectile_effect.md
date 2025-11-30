---
title: Explosive Projectile Effect
category: entities
---

# Explosive Projectile Effect

This entity defines a projectile that has an explosive effect upon impact.

## Key Components

### ShotEffectComponent

This component is responsible for applying the projectile's effect.

| Attribute        | Description                                     |
|------------------|-------------------------------------------------|
| `extra_modifier` | Specifies the type of effect to apply. Set to `"explosive_projectile"` for this entity. |

### LifetimeComponent

This component determines how long the projectile exists before despawning.

| Attribute | Description                               |
|-----------|-------------------------------------------|
| `lifetime`  | The duration in frames the projectile will exist. Set to `3600` (60 seconds). |

### InheritTransformComponent

This component is present but has no configurable attributes in this specific entity. It typically handles the inheritance of transformation properties from its parent.