---
title: Turret Left Entity
category: entities
---

# Turret Left Entity

This document describes the `turret_left.xml` entity, a variant of the standard turret found in Noita.

## Key Attributes

This entity inherits its base properties from `data/entities/animals/turret.xml`. The primary modifications are:

*   **DamageModelComponent**:
    *   `hp`: 9 (Hit Points)
    *   `max_hp`: 9 (Maximum Hit Points)
    *   `minimum_knockback_force`: 100000 (A very high value, indicating it's resistant to being knocked back)

*   **GameEffectComponent**:
    *   `effect`: `PROTECTION_FREEZE` (This entity is immune to freezing effects.)
    *   `frames`: -1 (The freeze protection is permanent.)

## Entity Structure

The entity is structured as follows:

```xml
<Entity>
  <Base file="data/entities/animals/turret_left.xml">
    <!-- Base turret properties -->
  </Base>

  <Entity>
    <InheritTransformComponent />
    <GameEffectComponent
        effect="PROTECTION_FREEZE"
        frames="-1"
    >
    </GameEffectComponent>
  </Entity>
</Entity>
```

### Base Entity

*   `Base file="data/entities/animals/turret_left.xml"`: This indicates that the entity inherits its fundamental properties from the `turret_left.xml` file itself, which is a common pattern for defining variations.

### Child Entity

*   `InheritTransformComponent`: This component ensures that the child entity inherits the position, rotation, and scale of its parent.
*   `GameEffectComponent`: This component applies a specific game effect to the entity. In this case, it grants permanent immunity to freeze effects.