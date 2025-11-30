---
title: Food Poisoning Protection Effect
category: entities
---

# Food Poisoning Protection Effect

This entity defines a game effect that grants protection against food poisoning.

## Key Components

### GameEffectComponent

This component is responsible for defining the actual game effect.

*   **`effect`**: `PROTECTION_FOOD_POISONING` - Specifies the type of protection granted.
*   **`frames`**: `-1` - Indicates that the effect is permanent (lasts indefinitely).
*   **`exclusivity_group`**: `0` - This likely means it can coexist with other effects in group 0.

### InheritTransformComponent

This component is present but empty, suggesting it might be a placeholder or intended for future use in inheriting transform properties.