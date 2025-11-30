---
title: Knockback Immunity Effect
category: entities
---

# Knockback Immunity Effect

This entity defines a temporary immunity to knockback effects in Noita.

## Key Components

### GameEffectComponent

This component grants the entity a specific game effect for a set duration.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `effect`  | The type of effect to apply.                    |
| `frames`  | The duration of the effect in game frames (60 frames = 1 second). |

**Example:**

```xml
<GameEffectComponent 
	effect="KNOCKBACK_IMMUNITY"
	frames="60"
></GameEffectComponent>
```