---
title: Remove Fog of War Effect
category: entities
---

# Remove Fog of War Effect

This entity defines a game effect that removes the fog of war for a specified duration.

## Key Components

### GameEffectComponent

This component is responsible for applying the game effect.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `effect`  | Specifies the type of effect to apply.    |
| `frames`  | The duration of the effect in game frames. |

**Example:**

```xml
<GameEffectComponent 
    effect="REMOVE_FOG_OF_WAR"
    frames="7200"
>
</GameEffectComponent >
```