---
title: Radioactivity Protection Effect
category: entities/misc
---

# Radioactivity Protection Effect

This entity defines a game effect that grants protection against radioactivity.

## Entity Definition

```xml
<Entity tags="effect_protection" >
    <!-- ... -->
</Entity>
```

## Key Components

### InheritTransformComponent

This component is present but empty, indicating that the entity does not have any specific transform properties that need to be inherited.

### GameEffectComponent

This is the core component that defines the game effect.

```xml
<GameEffectComponent
    _tags="effect_protection"
    effect="PROTECTION_RADIOACTIVITY"
    frames="-1"
    exclusivity_group="0"
></GameEffectComponent >
```

*   **`effect`**: Specifies the type of effect. In this case, it's `PROTECTION_RADIOACTIVITY`, meaning it will prevent or reduce damage from radioactive sources.
*   **`frames`**: Set to `-1`, indicating that this effect is permanent or lasts indefinitely until removed by other game mechanics.
*   **`exclusivity_group`**: Set to `0`. This likely means that this protection effect can stack with other effects in the same group or that it doesn't have any specific exclusivity constraints with other effects.