---
title: Melee Protection Effect
category: entities
---

# Melee Protection Effect

This entity defines a game effect that grants the player protection against melee damage.

## Entity Definition

The core of this entity is the `GameEffectComponent`.

### Key Components

*   **`GameEffectComponent`**:
    *   `_tags`: "effect_protection" - Identifies this as a protection effect.
    *   `effect`: "PROTECTION_MELEE" - Specifies the type of protection granted.
    *   `frames`: "-1" - Indicates the effect is permanent until removed.
    *   `exclusivity_group`: "0" - Defines its exclusivity group.

### Inheritance

*   **`InheritTransformComponent`**: This component is present but empty, suggesting it inherits standard transform properties.