---
title: Electricity Protection Effect
category: entities
---

# Electricity Protection Effect

This entity defines a game effect that grants the player protection against electricity.

## Key Components

### GameEffectComponent
This component is responsible for defining the actual game effect.

*   **`effect`**: `PROTECTION_ELECTRICITY` - Specifies the type of protection granted.
*   **`frames`**: `-1` - Indicates that the effect is permanent (lasts indefinitely).
*   **`exclusivity_group`**: `0` - This likely groups this effect with others, preventing certain other effects from being active simultaneously.

### InheritTransformComponent
This component is present but empty, suggesting it might be a placeholder or intended for future use in inheriting transform properties.